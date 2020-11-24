---
description: Need translations for your plugin? Use SuperCoreAPI Translations!
---

# Translations

### Creating a Translation

Here is an example of a translation:

```java
import xyz.theprogramsrc.supercoreapi.global.translations.Translation;
import xyz.theprogramsrc.supercoreapi.global.translations.TranslationManager;
import xyz.theprogramsrc.supercoreapi.global.translations.TranslationPack;

public enum Translations implements TranslationPack {

    MY_TRANSLATION("&6My Translation") 
    // The enum name will be used as key
    // in the translation file.
    ;
    
    private TranslationManager manager;
    private String value;
    
    Translations(String value){
        // Don't forget to initialize the value to save it later
        this.value = value;
    }
    
    @Override
    public Locale getLanguage() {
        // This is to indicate the name of the file, in this case "en_US.lang".
        // A single file can contain multiple translations, because the new
        // translations are added at the end of the file.
        return new Locale("en","US");
    }
    
    @Override
    public Translation get() {
        // This is a translation object. You can find more info here:
        // https://go.theprogramsrc.xyz/de71f
        return new Translation(this, this.name(), this.value);
    }

    @Override
    public List<Translation> translations() {
        // This maps all the enum objects into a translation list to register it
        // on the translation file
        return Arrays.stream(values()).map(Translations::get).collect(Collectors.toList());
    }

    @Override
    public void setManager(TranslationManager translationManager) {
        this.manager = translationManager;
    }

    @Override
    public TranslationManager getManager() {
        return manager;
    }

    @Override
    public String toString() {
        // If you override this method, later you can do:
        // "Prefix>>" + Translation.MY_TRANSLATION
        return this.get().translate();
    }
}
```

Now, to make this work you need to register the translation, you can do it in your main class \(That need to be extended to `SpigotPlugin` or `BungeePlugin`\) and add the following line of code to your `onPluginEnable` method: 

```java
@Override
public void onPluginEnable(){
    // ...
    this.registerTranslation(Translations.class);
    // ...
}
```

