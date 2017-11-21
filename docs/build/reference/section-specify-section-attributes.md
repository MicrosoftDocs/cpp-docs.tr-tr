---
title: "-BÖLÜMÜNE (bölüm özniteliklerini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /section
dev_langs: C++
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e3fd7e844d77b9a92408c0708542a4f8f5edf304
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="section-specify-section-attributes"></a>/SECTION (Bölüm Özniteliklerini Belirt)
```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /SECTION seçeneği bölümün .obj dosyasını derlendiğinde ayarlanmış öznitelikler geçersiz kılma bir bölüm özniteliklerini değiştirir.  
  
 Taşınabilir yürütülebilir (PE) dosyasındaki bir bölüm kesimi veya yeni bir yürütülebilir dosya (NE) dosyası kaynaklarında kabaca eşdeğerdir. Bölümler, kod veya verileri içerir. Kesimleri, bölümler bitişik bellek boyutu kısıtlamalar ile taşlarıdır. Bazı bölümler, kod veya programınız bildirilen ve diğer veri bölümleri sizin için bağlayıcı ve Kitaplığı Yöneticisi (lib.exe) tarafından oluşturulur ve işletim sistemi için önemli bilgiler içeren doğrudan kullanan veri içerir. Bilgi Bankası makalesi "Yürütülebilir dosyayı üstbilgi biçimi" (Q65122) NE dosyaları hakkında daha fazla bilgi için bkz. Bilgi Bankası makalelerini MSDN Kitaplığı'nda veya adresindeki bulabilirsiniz [http://support.microsoft.com](http://support.microsoft.com).  
  
 İki nokta üst üste (:) ve bir bölüm belirtin *adı*. *Adı* büyük küçük harfe duyarlıdır.  
  
 Standart adlarıyla çakışacak şekilde aşağıdaki adları kullanmayın. Örneğin, .sdata RISC platformlarda kullanılır:  
  
-   .arch  
  
-   .BSS  
  
-   .Data  
  
-   .edata  
  
-   .idata  
  
-   ve.xdata'yı  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   .sdata  
  
-   .srdata  
  
-   .Text  
  
-   Sanal işlem bulunur  
  
 Bölüm için bir veya daha fazla öznitelikleri belirtin. Aşağıda listelenen özniteliği karakterler büyük küçük harfe duyarlı değildir. Bölüm olmasını istediğiniz tüm öznitelikler belirtmeniz gerekir; belirtilmemiş bir öznitelik karakteri bu özniteliği bit kapatılmasına neden olur. R, W ya da E, varolan okuma, yazma belirtmeyin veya yürütülebilir durum değişmeden kalır varsa.  
  
 Bir öznitelik negate için kendi ünlem işareti (!) karakteriyle koyun. Öznitelik karakterleri anlamları aşağıda verilmiştir.  
  
|Karakter|Öznitelik|Açıklama|  
|---------------|---------------|-------------|  
|E|Yürütme|Yürütülebilir bir bölümdür|  
|R|Oku|Verileri okuma işlemlerine izin verir|  
|W|Write|Veri yazma işlemlerinin sağlar|  
|S|Shared|Görüntü yükleme tüm işlemler arasında bölüm paylaşır|  
|D|Discardable|Bölüm discardable olarak işaretler|  
|K|Önbelleğe alınabilir|Bölüm değil alınabilir olarak işaretler|  
|P|Disk belleğine alınabilir|Bölüm disk belleğine alınabilir değil olarak işaretler|  
  
 Negatif anlamda bunlara karşılık gelen bölüm bayrakların K ve P özgü bir seçenektir. Bunlardan birini .text bölümüne belirtirseniz (/ bölüm: .text, K), çalıştırdığınızda bölüm bayrakları fark olacaktır [DUMPBIN](../../build/reference/dumpbin-options.md) ile [/HEADERS](../../build/reference/headers.md) seçeneği; zaten örtük olarak önbelleğe. Varsayılan kaldırmak için /SECTION:.text belirttiğiniz! K ve DUMPBIN "Önbelleğe alınmaz." dahil olmak üzere, bölüm özellikleri gösterecek  
  
 Büyük olasılıkla E, R ya da ayarlamak W yok PE dosyasındaki bir bölümü geçersiz.  
  
 ALIGN *=#*  belirli bir bölüm için bir hizalama değeri belirtmenize olanak sağlar. Bkz: [/HİZALA](../../build/reference/align-section-alignment.md) daha fazla bilgi için.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)