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
ms.openlocfilehash: 0a52e9c9dcd53b01f17dc36825732b34771c75bb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492624"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Bölüm Özniteliklerini Belirt)

> **/Section:** _ad_, [[ **!** ] {**Masaüstü \ SW**}] [ **, ALIGN =** _sayı_]

## <a name="remarks"></a>Açıklamalar

**/Section** seçeneği bir bölümün özniteliklerini değiştirir, bölüm için. obj dosyası derlendiğinde ayarlanan öznitelikleri geçersiz kılar.

Taşınabilir çalıştırılabilir (PE) dosyasındaki bir *bölüm* , kod ya da veri içeren, adlandırılmış bir bellek bloğudur. Bazı bölümler, programınızın doğrudan bildirildiği ve kullandığı kod veya verileri içerir, ancak diğer veri bölümleri sizin için bağlayıcı ve kitaplık Yöneticisi (lib. exe) tarafından oluşturulur ve işletim sistemi için hayati öneme sahip bilgiler içerir. Daha fazla bilgi için bkz. [PE biçimi](/windows/win32/Debug/pe-format).

İki nokta üst üste belirtin (:) ve bölüm *adı*. *Ad* büyük/küçük harfe duyarlıdır.

Standart adlarla çakıştıkları için aşağıdaki adları kullanmayın. Örneğin,. sdata, RıSC platformlarında kullanılır:

- . Arch

- . bss

- . veri

- . edata

- . iDATA

- . pdata

- . rdata

- . reloc

- . RSRC

- . sbss

- . sdata

- . srdata

- . metin

- . xdata

Bölüm için bir veya daha fazla öznitelik belirtin. Aşağıda listelenen öznitelik karakterleri, büyük/küçük harfe duyarlı değildir. Bölümün sahip olmasını istediğiniz tüm öznitelikleri belirtmeniz gerekir; Atlanan bir öznitelik karakteri, öznitelik bitinin kapatılmasına neden olur. R, W veya E belirtmezseniz, var olan okuma, yazma veya çalıştırılabilir durumu değişmeden kalır.

Bir özniteliğe bir öznitelik eklemek için, karakterinin önüne bir ünlem işareti (!) getirin. Öznitelik karakterlerinin anlamları bu tabloda gösterilmiştir:

|Karakter|Öznitelik|Açıklama|
|---------------|---------------|-------------|
|E|Yürütme|Bölüm yürütülebilir|
|R|Oku|Verilerde okuma işlemlerine izin verir|
|W|Write|Verilerde yazma işlemlerine izin verir|
|S|Shared|Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır|
|D|Discardable|Bölümü discardable olarak işaretler|
|K|Önbelleğe alınabilir öğeleri|Bölümü önbelleklenebilir olarak işaretler|
|P|Alınabilen|Bölümü sayfalanabilir olarak işaretler|

K ve P, bunlara karşılık gelen bölüm bayraklarının negatif anlamda kullanıldığı şekilde olağan dışı bir şekilde kullanılır. **/Section:. Text, K** seçeneğini kullanarak bunlardan birini. Text bölümünde belirtirseniz, [/Headers](headers.md) seçeneğiyle [dumpbin](dumpbin-options.md) çalıştırdığınızda bölüm bayraklarının herhangi bir farklılık yoktur; Bölüm zaten örtük olarak önbelleğe alındı. Varsayılanı kaldırmak için **/section:. Text,! değerini belirtin.** Bunun yerine K. DUMPBIN, "önbelleğe alınmamış" dahil olmak üzere bölüm özelliklerini açığa çıkarır.

PE dosyasında E, R veya W kümesi olmayan bir bölüm büyük olasılıkla geçersizdir.

**ALIGN =** _Number_ bağımsız değişkeni, belirli bir bölüm için bir hizalama değeri belirtmenize olanak tanır. _Sayı_ bağımsız değişkeni bayt cinsinden ve ikinin üssü olmalıdır. Daha fazla bilgi için bkz. [/align](align-section-alignment.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > bağlayıcıkomut > **satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin. Değişikliği uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
