1. export const NativeIconAPI =
  NativeModules.RNVectorIconsManager || NativeModules.RNVectorIconsModule;


2. getImageForFontSync

        // 同步
        const imagePath = NativeIconAPI.getImageForFontSync

        // 异步
        const imagePath =await NativeIconAPI.getImageForFont

3. loadFontWithFileName