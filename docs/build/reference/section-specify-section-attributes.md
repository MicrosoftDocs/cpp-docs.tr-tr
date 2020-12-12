---
description: Daha fazla bilgi edinin:/SECTION (bölüm özniteliklerini belirt)
title: /SECTION (Bölüm Özniteliklerini Belirt)
ms.date: 12/29/2017
f1_keywords:
- /section
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
ms.openlocfilehash: 8731f720e04ae2893f288e4b96aeaa019af43350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224796"
---
# <a name="section-specify-section-attributes"></a>/SECTION (Bölüm Özniteliklerini Belirt)

> **/Section:**_ad_, [[**!**] {**Masaüstü \ SW**}] [**, ALIGN =**_sayı_]

## <a name="remarks"></a>Açıklamalar

**/Section** seçeneği bir bölümün özniteliklerini değiştirir, bölüm için. obj dosyası derlendiğinde ayarlanan öznitelikleri geçersiz kılar.

Taşınabilir çalıştırılabilir (PE) dosyasındaki bir *bölüm* , kod ya da veri içeren, adlandırılmış bir bellek bloğudur. Bazı bölümler, programınızın ve kitaplık Yöneticisi (lib.exe) tarafından sizin için diğer veri bölümlerinin oluşturulması ve işletim sistemi için önemli bilgiler içermesi sırasında, programınızın doğrudan bildirildiği ve kullandığı kod veya verileri içerir. Daha fazla bilgi için bkz. [PE biçimi](/windows/win32/Debug/pe-format).

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

|Karakter|Öznitelik|Anlamı|
|---------------|---------------|-------------|
|E|Yürütme|Bölüm yürütülebilir|
|R|Okuma|Verilerde okuma işlemlerine izin verir|
|W|Yazma|Verilerde yazma işlemlerine izin verir|
|S|Paylaşılan|Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır|
|D|Discardable|Bölümü discardable olarak işaretler|
|K|Önbelleğe alınabilir öğeleri|Bölümü önbelleklenebilir olarak işaretler|
|P|Alınabilen|Bölümü sayfalanabilir olarak işaretler|

K ve P, bunlara karşılık gelen bölüm bayraklarının negatif anlamda kullanıldığı şekilde olağan dışı bir şekilde kullanılır. **/Section:. Text, K** seçeneğini kullanarak bunlardan birini. Text bölümünde belirtirseniz, [/Headers](headers.md) seçeneğiyle [dumpbin](dumpbin-options.md) çalıştırdığınızda bölüm bayraklarının herhangi bir farklılık yoktur; Bölüm zaten örtük olarak önbelleğe alındı. Varsayılanı kaldırmak için **/section:. Text,! değerini belirtin.** Bunun yerine K. DUMPBIN, "önbelleğe alınmamış" dahil olmak üzere bölüm özelliklerini açığa çıkarır.

PE dosyasında E, R veya W kümesi olmayan bir bölüm büyük olasılıkla geçersizdir.

**ALIGN =**_Number_ bağımsız değişkeni, belirli bir bölüm için bir hizalama değeri belirtmenize olanak tanır. _Sayı_ bağımsız değişkeni bayt cinsinden ve ikinin üssü olmalıdır. Daha fazla bilgi için bkz. [/align](align-section-alignment.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin. Değişikliği uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
