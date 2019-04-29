---
title: /SECTION (Bölüm Özniteliklerini Belirt)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 8fb73043c9c185adee0859bb81098eab022430c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318569"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Bölüm Özniteliklerini Belirt)

> **/ SECTION:**_adı_, [[**!**] {**DEKPRSW**}] [**, ALIGN =**_numarası_]

## <a name="remarks"></a>Açıklamalar

**/SECTION** seçeneği öznitelik bölüm için .obj dosyası derlendiğinde kümesini geçersiz kılma, bir bölümün özniteliklerini değiştirir.

A *bölümü* adlandırılmış bir blok kod veya veri içeren belleğin bir taşınabilir yürütülebilir (PE) dosyasıdır. Bazı bölümler, kod veya programınızın bildirildi ve diğer veri bölümleri sizin için Kitaplık Yöneticisi'ni (lib.exe) ve bağlayıcı tarafından oluşturulur ve işletim sistemine önemli bilgiler içeren doğrudan kullanan veri içerir. Daha fazla bilgi için [PE biçimi](/windows/desktop/Debug/pe-format).

İki nokta üst üste (:) ve bölüm belirtin *adı*. *Adı* büyük/küçük harfe duyarlıdır.

Bunlar standart adlarla çakışıp olarak aşağıdaki adları kullanmayın. Örneğin, .sdata RISC platformlarda kullanılır:

- .arch

- .bss

- .data

- .edata

- .idata

- .pdata

- .rdata

- .reloc

- .rsrc

- .sbss

- .sdata

- .srdata

- .Text

- Sanal işlem bulunur

Bölüm için bir veya daha fazla öznitelikleri belirtin. Aşağıda listelenen öznitelik karakterleri, büyük küçük harfe duyarlı değildir. Bölüm olmasını istediğiniz tüm öznitelikleri belirtmeniz gerekir; belirtilmemiş öznitelik karakteri, söz konusu öznitelik bit devre dışı bırakılması neden olur. R, G veya E, mevcut okuma, yazma belirtmeyin veya yürütülebilir durumu değişmediğinden olur.

Bir öznitelik negatif yapılacak, ünlem işareti (!) karakteriyle koyun. Öznitelik karakterleri anlamları bu tabloda gösterilmiştir:

|Karakter|Öznitelik|Açıklama|
|---------------|---------------|-------------|
|E|Yürütme|Yürütülebilir bir bölümdür|
|R|Oku|Veri okuma işlemlerinin sağlar|
|W|Write|Veri yazma işlemleri sağlar.|
|S|Shared|Resmi yüklemek tüm işlemler arasında bölümü paylaşır|
|D|Discardable|Bölüm discardable olarak işaretler.|
|K|Önbelleğe alınabilir|Bölüm önbelleğe alınabilir değil olarak işaretler.|
|P|Alınabilir|Bölüm alınabilir değil olarak işaretler.|

K P kendisine karşılık gelen bölüm bayrakları negatif anlamda kullanılır, olağan değildir. Bunlardan biri .text bölümünü kullanarak belirtirseniz **/SECTION:.text, K** seçeneği, bölüm bayrakları fark çalıştırdığınızda [DUMPBIN](dumpbin-options.md) ile [OPTIONAL](headers.md)seçeneği; Bölümü örtük olarak zaten önbelleğe. Varsayılan kaldırmak için bu seçeneği belirtin **/SECTION:.text,! K** yerine. DUMPBIN "Önbelleğe alınmaz." dahil olmak üzere, bölüm özellikleri gösterir.

Büyük olasılıkla E, R ya da ayarlanmış W yok PE dosyasının bir bölümünde geçersiz.

**HİZALA =**_numarası_ bağımsız değişkeni bir hizalama değeri belirli bir bölümü için belirtmenize olanak sağlar. _Numarası_ bağımsız değişkeni bayt ve ikinin üssü olmalıdır. Bkz: [/hizalama](align-section-alignment.md) daha fazla bilgi için.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
