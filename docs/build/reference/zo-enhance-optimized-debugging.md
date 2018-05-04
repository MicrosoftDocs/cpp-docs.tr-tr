---
title: -Zo (en iyi duruma getirilmiş hata ayıklamayı iyileştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 013738ab05bf67d3db066d94d32d398a0555c55e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (En İyi Duruma Getirilmiş Hata Ayıklamayı İyileştirme)
İyileştirilmiş kod için Gelişmiş hata ayıklama bilgisi olmayan hata ayıklama derlemelerinde oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
/Zo[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/Zo** derleyici anahtarı en iyi duruma getirilmiş kodu için Gelişmiş hata ayıklama bilgileri oluşturur. En iyi duruma getirme kayıtları için yerel değişkenler kullanın, kodu yeniden Sırala, döngüler ve satır içi işlev çağrılarını vectorize. Bu iyileştirmeler, kaynak kodu ve derlenen nesne kodu arasındaki ilişkiyi soyutlamaması. **/Zo** anahtar, yerel değişkenleri ve satır içi işlevler için ek hata ayıklama bilgileri oluşturmak için derleyici söyler. Değişkenleri görmek için kullanmak **otomobiller**, **Yereller**, ve **izleme** adım adım windows iyileştirilmiş kodda Visual Studio hata ayıklayıcısında. Ayrıca, satır içi işlevler WinDBG Hata Ayıklayıcısı'ndaki göstermek Yığın izlemeleri sağlar. Hata ayıklama iyileştirmeleri devre dışı bırakmış derlemeleri ([/Od](../../build/reference/od-disable-debug.md)) oluşturulduğunda ek hata ayıklama bilgisi gerekmez **/Zo** belirtilir. Kullanım **/Zo** açık iyileştirme hata ayıklama yayın yapılandırmaları için anahtar. En iyi duruma getirme anahtarları hakkında daha fazla bilgi için bkz: [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md). **/Zo** seçeneği varsayılan olarak etkinleştirilmiştir Visual Studio'da hata ayıklama bilgileri belirttiğinizde **/zı** veya **/Z7**. Belirtin **/Zo-** açıkça Bu derleyici seçeneği devre dışı bırakmak için.  
  
 **/Zo** Visual Studio 2013 güncelleştirme 3'te başlangıç anahtarı kullanılabilir ve daha önce belgelenmemiş yerini **/d2Zi+** geçin.  
  
### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio'da /Zo derleyici seçeneği ayarlamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik `/Zo` ve ardından **Tamam**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)   
 [/ Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md)   
 [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue)