---
title: 'HLSL özellik sayfaları: Genel | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cc9a44076999633fd17b049cbcfad75f65eb7e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33340144"
---
# <a name="hlsl-property-pages-general"></a>HLSL Özellik Sayfaları: Genel
HLSL derleyici (fxc.exe) aşağıdaki özellikleri yapılandırmak için kullanın, **genel** özellik sayfası. Nasıl erişileceği hakkında bilgi için **genel** özellik sayfası HLSL klasöründeki bkz [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Ek içeren dizinler**  
 Bir veya daha fazla dizinleri INCLUDE yolu ekler. Dizinleri ayırmak için noktalı kullanın.  
  
 Bu özellik karşılık gelen **/I [path]** komut satırı bağımsız değişkeni.  
  
 **Giriş noktası adı**  
 Giriş noktası için gölgelendirici belirtir. Varsayılan değer olan **ana**.  
  
 Bu özellik karşılık gelen **/E [name]** komut satırı bağımsız değişkeni.  
  
 **İyileştirmeleri devre dışı bırak**  
 **Evet (/ Od)** iyileştirmeler; devre dışı bırakmak için Aksi halde, **Hayır**. Varsayılan değer olan **Evet (/ Od)** için **hata ayıklama** yapılandırmaları ve **Hayır** için **sürüm** yapılandırmaları.  
  
 **/Od** HLSL derleyici komut satırı bağımsız değişkeni örtük olarak geçerlidir **/Gfp** komut satırı bağımsız değişkeni, ancak çıktı olmayabilir her ikisi de geçirerek üretilen çıkış aynı **/Od**  ve **/Gfp** komut satırı bağımsız değişkenleri açıkça.  
  
 **Hata ayıklama bilgisi etkinleştir**  
 **Evet (/zı)** hata ayıklama bilgilerini; etkinleştirmek için Aksi halde, **Hayır**. Varsayılan değer olan **(/Zi) Evet** için **hata ayıklama** yapılandırmaları ve **Hayır** için **sürüm** yapılandırmaları.  
  
 **Gölgelendirici türü**  
 Gölgelendirici türünü belirtir. Gölgelendiriciler farklı türde grafik ardışık düzen farklı kısımlarını uygulayın. Gölgelendiriciler belirli türdeki yalnızca daha yeni gölgelendirici modellerinde kullanılabilir (hangi belirtilen tarafından **gölgelendirici modeli** özelliği) — Örneğin, gölgelendiriciler gölgelendirici modeli 5 sunuldu işlem.  
  
 Bu özellik karşılık gelen **[türü]** kısmı **/T [türü] _ [model]** HLSL derleyici komut satırı bağımsız değişkeni. **Gölgelendirici modelleri** özellik belirtir **[model]** bağımsız değişkeni kısmı.  
  
 **Gölgelendirici modeli**  
 Gölgelendirici modeli belirtir. Farklı gölgelendirici modelleri farklı özellikler vardır. Genel olarak, daha yeni gölgelendirici modelleri genişletilmiş özellikler sunar ancak gölgelendirici kodu çalıştırmak için daha modern grafik donanım gerektirir. Belirli türdeki gölgelendiriciler (tarafından belirtilir **gölgelendirici türü** özelliği) yalnızca daha yeni gölgelendirici modellerinde kullanılabilir — örneğin, gölgelendiriciler gölgelendirici modeli 5 sunuldu işlem.  
  
 Bu özellik karşılık gelen **[model]** kısmı **/T [türü] _ [model]** HLSL derleyici komut satırı bağımsız değişkeni. **Gölgelendirici türü** özellik belirtir **[türü]** bağımsız değişkeni kısmı.  
  
 **Önişlemci tanımları**  
 HLSL kaynak kodu dosyasına uygulamak için bir veya daha fazla önişlemci sembolü tanımları ekler. Simge tanımlarını ayırmak için noktalı kullanın.  
  
 Bu özellik karşılık gelen **/D [tanımları]** HLSL derleyici komut satırı bağımsız değişkeni.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HLSL özellik sayfaları](../ide/hlsl-property-pages.md)   
 [HLSL özellik sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)   
 [HLSL Özellik Sayfaları: Çıktı Dosyaları](../ide/hlsl-property-pages-output-files.md)