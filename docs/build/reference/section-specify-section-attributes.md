---
title: "/ SECTION (bölüm özniteliklerini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa214c7efeeee595300204df900a333258052772
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="section-specify-section-attributes"></a>/SECTION (Bölüm Özniteliklerini Belirt)

> **/ SECTION:**_adı_, [[**!**] {**DEKPRSW**}] [**, HİZALA =**_numarası_]

## <a name="remarks"></a>Açıklamalar

**/SECTION** seçeneği bölümün .obj dosyasını derlendiğinde ayarlanmış öznitelikler geçersiz kılma bir bölüm özniteliklerini değiştirir.

A *bölüm* taşınabilir yürütülebilir (PE) içinde bir adlandırılmış bitişik bir kod veya veri içeren bellek bloğu dosyasıdır. Bazı bölümler, kod veya programınız bildirilen ve diğer veri bölümleri sizin için bağlayıcı ve Kitaplığı Yöneticisi (lib.exe) tarafından oluşturulur ve işletim sistemi için önemli bilgiler içeren doğrudan kullanan veri içerir. Daha fazla bilgi için bkz: [PE biçimi](https://msdn.microsoft.com/library/windows/desktop/ms680547).

İki nokta üst üste (:) ve bir bölüm belirtin *adı*. *Adı* büyük küçük harfe duyarlıdır.

Standart adlarla çakışıyor gibi aşağıdaki adları kullanmayın. Örneğin, .sdata RISC platformlarda kullanılır:

- .arch

- .BSS

- .Data

- .edata

- .idata

- ve.xdata'yı

- .rdata

- .reloc

- .rsrc

- .sbss

- .sdata

- .srdata

- .Text

- Sanal işlem bulunur

Bölüm için bir veya daha fazla öznitelikleri belirtin. Aşağıda listelenen özniteliği karakterler büyük küçük harfe duyarlı değildir. Bölüm olmasını istediğiniz tüm öznitelikler belirtmeniz gerekir; belirtilmemiş bir öznitelik karakteri bu özniteliği bit kapatılmasına neden olur. R, W ya da E, varolan okuma, yazma belirtmeyin veya yürütülebilir durum değişmeden kalır varsa.

Bir öznitelik negate için kendi ünlem işareti (!) karakteriyle koyun. Öznitelik karakterleri anlamları bu tabloda gösterilmiştir:

|Karakter|Öznitelik|Açıklama|
|---------------|---------------|-------------|
|E|Yürütme|Yürütülebilir bir bölümdür|
|R|Oku|Verileri okuma işlemlerine izin verir|
|W|Write|Veri yazma işlemlerinin sağlar|
|S|Shared|Görüntü yükleme tüm işlemler arasında bölüm paylaşır|
|D|Discardable|Bölüm discardable olarak işaretler|
|K|Önbelleğe alınabilir|Bölüm değil alınabilir olarak işaretler|
|P|Disk belleğine alınabilir|Bölüm disk belleğine alınabilir değil olarak işaretler|

Kendisine karşılık gelen bölüm bayrakları negatif anlamda kullanılan K ve P olağan dışı bir seçenektir. Bunlardan birini .text bölümünü kullanarak belirtirseniz **/SECTION:.text, K** seçeneği, çalıştırdığınızda bölüm bayrakları fark eder [DUMPBIN](../../build/reference/dumpbin-options.md) ile [/HEADERS](../../build/reference/headers.md)seçeneği; bölüm zaten örtük olarak önbelleğe alınmadı. Varsayılan kaldırmak için belirtmek **/SECTION:.text,! K** yerine. DUMPBIN "Önbelleğe alınmaz." dahil olmak üzere, bölüm özellikleri gösterir

Büyük olasılıkla E, R ya da ayarlamak W yok PE dosyasındaki bir bölümü geçersiz.

**HİZALA =**_numarası_ bağımsız değişkeni belirli bir bölüm için bir hizalama değeri belirtmenize olanak sağlar. _Numarası_ bağımsız değişkeni bayt ve iki gücünü olması gerekir. Bkz: [/HİZALA](../../build/reference/align-section-alignment.md) daha fazla bilgi için.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçenek girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
