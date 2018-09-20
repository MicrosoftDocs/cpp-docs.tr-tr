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
ms.openlocfilehash: f29228fb7744f93014ba35b75ed5a42d6531cd28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376999"
---
# <a name="hlsl-property-pages-general"></a>HLSL Özellik Sayfaları: Genel

HLSL derleyicisi (fxc.exe) aşağıdaki özellikleri yapılandırmak için kullanın, **genel** özellik sayfası. Nasıl erişileceği hakkında daha fazla bilgi için **genel** HLSL klasöründe, özellik sayfasında bakın [Working with Project Properties](../ide/working-with-project-properties.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Ek içeren dizinler**

   Bir veya daha fazla dizin yoluna ekler. Dizinleri birbirinden ayırmak için noktalı virgül kullanın.

Bu özellik için karşılık gelen **/I [yol]** komut satırı bağımsız değişkeni.

- **Giriş noktası adı**

   Gölgelendirici için giriş noktasını belirtir. Varsayılan değer olan **ana**.

Bu özellik için karşılık gelen **/E [name]** komut satırı bağımsız değişkeni.

- **İyileştirmeleri devre dışı bırak**

   **Evet (/ Od)** ; iyileştirmeleri devre dışı bırakmak için Aksi takdirde, **Hayır**. Varsayılan değer olan **Evet (/ Od)** için **hata ayıklama** yapılandırmaları ve **Hayır** için **yayın** yapılandırmaları.

**/Od** HLSL derleyici komut satırı bağımsız değişkeni örtük olarak geçerlidir **/gfp** komut satırı bağımsız değişkeni, ancak çıkış olabilir hem de geçirerek üretilen çıktısına benzer **/Od**  ve **/gfp** komut satırı bağımsız değişkenlerini açıkça.

- **Hata ayıklamayı etkinleştir bilgileri**

   **Evet (/Zi)** etkinleştirme hata ayıklama bilgilerini; Aksi takdirde, **Hayır**. Varsayılan değer olan **Evet (/Zi)** için **hata ayıklama** yapılandırmaları ve **Hayır** için **yayın** yapılandırmaları.

- **Gölgelendirici türü**

   Gölgelendirici türünü belirtir. Farklı türde gölgelendiricileri grafik ardışık düzen farklı bölümlerine uygulayın. Belirli türde bir gölgelendirici yalnızca son gölgelendirici modelleri kullanılabilir (tarafından belirtilir **gölgelendirici modeli** özelliği) — örneğin gölgelendiricileri gölgelendirici modeli 5 sunulmuştur işlem.

   Bu özellik için karşılık gelen  **\[türü]** kısmı **/T \[türü] _\[modeli]** HLSL derleyici komut satırı bağımsız değişkeni. **Gölgelendirici modelleri** özellik belirtir **[model]** bağımsız değişkeni bir kısmı.

- **Gölgelendirici modeli**

   Gölgelendirici modelini belirtir. Farklı gölgelendirici modelleri, farklı özelliklere sahip. Genel olarak, daha yeni gölgelendirici modelleriyle genişletilmiş özellikler sunar ancak gölgelendirici kodu çalıştırmak için daha modern grafik donanımı gerektirir. Gölgelendiricileri belirli türdeki (tarafından belirtilir **gölgelendirici türünü** özelliği) yalnızca daha yeni gölgelendirici modelleriyle kullanılabilir — örneğin gölgelendiricileri gölgelendirici modeli 5 sunulmuştur işlem.

   Bu özellik için karşılık gelen  **\[modeli]** kısmı **/T \[türü] _\[modeli]** HLSL derleyici komut satırı bağımsız değişkeni. **Gölgelendirici türünü** özellik belirtir **[türü]** bağımsız değişkeni bir kısmı.

- **Önişlemci tanımları**

   HLSL kaynak kod dosyasına uygulanacak bir veya daha çok önişlemci sembol tanımlarını ekler. Sembol tanımlarını ayırmak için noktalı virgül kullanın.

   Bu özellik için karşılık gelen **/D \[tanımları]** HLSL derleyici komut satırı bağımsız değişkeni.

## <a name="see-also"></a>Ayrıca Bkz.

[HLSL Özellik Sayfaları](../ide/hlsl-property-pages.md)<br>
[HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)<br>
[HLSL Özellik Sayfaları: Çıktı Dosyaları](../ide/hlsl-property-pages-output-files.md)