---
title: Kaynak Derleyicisi Hatası RW2002
ms.date: 11/04/2016
f1_keywords:
- RW2002
helpviewer_keywords:
- RW2002
ms.assetid: b1d1a49b-b50b-4b0b-9f09-c7762e2dbe8f
ms.openlocfilehash: 1726e6ce74dfd7b6b0c6e4b69771a826cdf07774
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71230415"
---
# <a name="resource-compiler-error-rw2002"></a>Kaynak Derleyicisi Hatası RW2002

Ayrıştırma hatası

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. **Hızlandırıcı türü gerekli (ASCII veya VIRTKEY)**

   `type` **Hızlandırıcılar** deyimindeki alan, ASCII ya da virtkey değerini içermelidir.

1. **Hızlandırıcı tablosunda başlatma bekleniyor**

   **BEGIN** anahtar sözcüğü, **Hızlandırıcılar** anahtar sözcüğünü hemen izlemelidir.

1. **İletişim kutusunda BEGIN bekleniyor**

   **BEGIN** anahtar sözcüğü hemen **iletişim kutusuna** gelmelidir.

1. **Menüde BEGIN bekleniyor**

   **BEGIN** anahtar sözcüğü hemen **menü** anahtar sözcüğünü izlemelidir.

1. **RCData 'da BEGIN bekleniyor**

   **BEGIN** anahtar sözcüğü, **rcdata** anahtar sözcüğünü hemen izlemelidir.

1. **Dize tablosunda BEGIN anahtar sözcüğü bekleniyor**

   **BEGIN** anahtar sözcüğü, **StringTable** anahtar sözcüğünü hemen izlemelidir.

1. **Dize sabitleri yeniden kullanılamaz**

   **StringTable** bildiriminde aynı değeri iki kez kullanıyorsunuz. Çakışan ondalık ve onaltılık değerleri karıştırdığınızdan emin olun. **StringTable** içindeki her bir kimlik benzersiz olmalıdır. En yüksek verimlilik için, 16 ' dan başlayan bitişik sabitleri kullanın.

1. **Denetim karakteri Aralık dışında [^ A-^ Z]**

   **Hızlandırıcılar** deyimindeki bir denetim karakteri geçersiz. Şapka işaretini () izleyen karakter **^** ve Z (dahil) arasında olmalıdır.

1. **Boş menülere izin verilmiyor**

   Bir **End** anahtar sözcüğü **menü** ifadesinde herhangi bir menü öğesi tanımlanmadan önce görüntülenir. Kaynak derleyicisi boş menülere izin vermiyor. **Menü** bildiriminde açık tırnak işareti olmadığından emin olun.

1. **İletişim kutusunda BITIŞ bekleniyor**

   **End** anahtar sözcüğü bir **iletişim kutusu** ifadesinin sonunda gerçekleşmelidir. Yukarıdaki deyimden kalan açık tırnak bulunmadığından emin olun.

1. **Menüde BITIŞ bekleniyor**

   **End** anahtar sözcüğü bir **menü** ifadesinin sonunda gelmelidir. Açık tırnak işaretleri veya eşleşmeyen bir **Başlangıç** ve **bitiş** deyimleri çiftinin olmadığından emin olun.

1. **Hızlandırıcı tablosunda virgül bekleniyor**

   Kaynak derleyicisi, `event` **Hızlandırıcılar** deyimindeki ve *ıdvalue* alanları arasında virgül gerektirir.

1. **Beklenen denetim sınıfı adı**

   **İletişim deyimindeki** bir **Denetim** ifadesinin alanıaşağıdakitürlerdenbiriolmalıdır:`class` DÜĞME, AÇıLAN kutusu, düzenleme, LISTBOX, KAYDıRMA çubuğu, STATIK veya Kullanıcı tanımlı. Sınıfın doğru yazıldığından emin olun.

1. **Beklenen yazı tipi yüzü adı**

   **İletişim** deyimindeki FONT *seçeneğinin yazı tipi alanı,* çift tırnak IŞARETI içine alınmış bir ASCII karakter dizesi olmalıdır. Bu alan bir yazı tipinin adını belirtir.

1. **MenuItem için beklenen KIMLIK değeri**

   **Menü** Ifadesinin bir *menuid* alanı içermesi gerekir ve bu, menü kaynağını tanımlayan adı veya sayıyı belirtir.

1. **Beklenen menü dizesi**

   Her **MenuItem** ve **Popup** deyimlerinin, menü öğesinin veya açılan menünün adını belirten çift tırnak işareti içine alınmış bir dize olan bir *metin* alanı içermesi gerekir. **MENUıTEM ayırıcı** deyimleri, tırnak işareti gerektirmez.

1. **Beklenen sayısal komut değeri**

   Kaynak derleyicisi, **Hızlandırıcılar** bildiriminde bir sayısal *ıdvalue* alanı bekliyordu. Değeri belirtmek için bir `#define` sabit kullandıysanız ve sabitin doğru yazıldığından emin olun.

1. **Dize tablosunda sayısal sabit bekleniyor**

   Bir `#define` ifadede tanımlanan sayısal bir sabit, bir **StringTable** deyimindeki **BEGIN** anahtar sözcüğünü hemen izlemelidir.

1. **Beklenen sayısal nokta boyutu**

   **İletişim** deyimindeki yazı tipi seçeneğinin *Pointsize* alanı bir tamsayı noktası boyutu değeri olmalıdır.

1. **Sayısal iletişim kutusu sabiti bekleniyor**

   Bir **Iletişim kutusu** , *x, y, Genişlik*ve *Yükseklik* alanları için tamsayı değerleri gerektirir. Bu değerlerin, **iletişim** anahtar sözcüğünden sonra eklendiğinden ve olumsuz olmadıklarından emin olun.

1. **STRINGTABLE içinde beklenen dize**

   **StringTable** deyimindeki her *strıngıd* değerinden sonra bir dize bekleniyor.

1. **Beklenen dize veya sabit Hızlandırıcı komutu**

   Kaynak derleyicisi hızlandırıcı için ne tür bir anahtar ayarlanmakta olduğunu saptayamadı. `event` **Hızlandırıcılar** deyimindeki alan geçersiz olabilir.

1. **KIMLIK için sayı bekleniyor**

   **İletişim** deyimindeki bir denetim ifadesinin `id` alanı için bir sayı bekleniyor. Denetim kimliği için bir sayı veya `#define` deyiminiz olduğundan emin olun.

1. **İletişim sınıfında tırnak içinde dize bekleniyor**

   **DIALOG deyimindeki** Class seçeneğinin alanı,çifttırnakişaretiiçinealınmışbirtamsayıveyadize`class` olmalıdır.

1. **İletişim kutusunda tırnak işaretli dize bekleniyor**

   DIALOG `captiontext` deyimindeki CAPTION seçeneğinin alanı, çift tırnak işareti içine alınmış bir ASCII karakter dizesi olmalıdır.

1. **Dosya bulunamadı: dosya adı**

   Kaynak derleyicisi komut satırında belirtilen dosya bulunamadı. Dosyanın başka bir dizine taşınıp taşınmadığını ve dosya adının veya yolun doğru yazıldığından emin olun. Dosyalar, varsa **Include** ortam değişkeni veya Visual Studio ayarı kullanılarak aranır.

1. **Yazı tipi adları sıra sayıları olmalıdır**

   FONT deyimindeki *Pointsize* alanı bir dize değil tamsayı olmalıdır.

1. **Geçersiz Hızlandırıcı**

   Hızlandırıcılar `event` deyimindeki bir alan tanınmıyor veya en fazla iki karakter uzunluğunda.

1. **Geçersiz Hızlandırıcı türü (ASCII veya VIRTKEY)**

   `type` **Hızlandırıcılar** deyimindeki alan, ASCII ya da virtkey değerini içermelidir.

1. **Geçersiz denetim karakteri**

   **Hızlandırıcılar** deyimindeki bir denetim karakteri geçersiz. Geçerli bir denetim karakteri, bir giriş işaretinden (yalnızca) (^) sonraki bir harfle (yalnızca) oluşur.

1. **Geçersiz denetim türü**

   Bir **Iletişim kutusundaki** her denetim ifadesinin aşağıdakilerden biri olması gerekir: CHECKBOX, COMBOBOX, CONTROL, CTEXT, DEFBASMA, EDITTEXT, GROUPBOX, ICON, LISTBOX, LTEXT, BASMCON, RADIOBUTTON, RTEXT, KAYDIRMA ÇUBUĞU. Bu denetim deyimlerinin doğru yazıldığından emin olun.

1. **Geçersiz tür**

   Kaynak türü, WINDOWS. h dosyasında tanımlanan türler arasında değildi.

1. **Denetimde beklenen metin dizesi veya sıra sayısı**

   **İletişim** deyimindeki bir **Denetim** ifadesinin *metin* alanı, denetim türüne bir metin dizesi veya bir sıralı başvuru olmalıdır. Sıra kullanılıyorsa, denetim için bir `#define` deyiminiz olduğundan emin olun.

1. **Eşleşmeyen parantezler**

   **Iletişim kutusunda** tüm açık parantezleri kapattığınızdan emin olun.

1. **RCData içinde beklenmeyen değer**

   **Rcdata** deyimindeki *ham veri* değerleri, her biri virgülle ayrılmış tamsayılar veya dizeler olmalıdır. Bir dize etrafında bir virgül bırakmadığınızdan veya tırnak işareti bırakmadığınızdan emin olun.

1. **Bilinmeyen menü alt türü**

   **Menü** ifadesinin *öğe tanımı* alanı yalnızca **MenuItem** ve **Popup** deyimlerini içerebilir.