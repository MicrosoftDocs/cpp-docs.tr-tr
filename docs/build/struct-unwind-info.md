---
title: struct UNWIND_INFO
ms.date: 11/04/2016
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
ms.openlocfilehash: 0130d30c314a7736ffaf24753a2e6fdf9ad55b12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517045"
---
# <a name="struct-unwindinfo"></a>struct UNWIND_INFO

Geriye doğru izleme veri bilgisi yapısı, yığın işaretçisi ve kalıcı kayıtlar yığında kaydedildiği bir işleve sahip etkileri kaydetmek için kullanılır:

|||
|-|-|
|UBYTE: 3|Sürüm|
|UBYTE: 5|Bayraklar|
|UBYTE|Giriş boyutu|
|UBYTE|Geriye doğru izleme kodları sayısı|
|UBYTE: 4|Çerçeve kaydı|
|UBYTE: 4|Çerçeve kaydı uzaklık (ölçeği)|
|USHORT \* n|Bırakma kodları dizisi|
|değişken|Formun (1) veya (2) aşağıda olabilir|

(1) özel durum işleyicisi

|||
|-|-|
|ULONG|Özel durum işleyicisinin adresi|
|değişken|Dile özel işleyici veriler (isteğe bağlı)|

(2) Zincirleme Bırakma bilgi

|||
|-|-|
|ULONG|Başlangıç adresi işlevi|
|ULONG|Bitiş adresi işlevi|
|ULONG|Bırakma bilgisi adresi|

UNWIND_INFO yapısını bellekte DWORD hizalanmış olmalıdır. Her bir alan anlamını aşağıdaki gibidir:

- **Sürüm**

   Geriye doğru izleme verileri, şu anda 1 sürüm numarası.

- **bayrakları**

   Üç bayraktan şu anda tanımlanır:

   |Bayrağı|Açıklama|
   |-|-|
   |`UNW_FLAG_EHANDLER`| İşlevi, özel durumları incelemek için gereken işlevleri ararken çağrılması gereken bir özel durum işleyicisine sahiptir.|
   |`UNW_FLAG_UHANDLER`| İşlev bir özel durumu geriye doğru izleme sırasında çağrılması gereken bir sonlandırma işleyicisi sahiptir.|
   |`UNW_FLAG_CHAININFO`| Bu bilgileri yapısı, birincil bir yordam değil geriye doğru. Bunun yerine, zincirleme bir önceki RUNTIME_FUNCTION girişi içeriğini girdidir bilgilerindeki. Aşağıdaki metni bir açıklaması için bkz: zincirleme bırakma bilgi yapıları. Bu bayrağı ayarlarsanız, UNW_FLAG_EHANDLER ve UNW_FLAG_UHANDLER bayrakları temizlenmelidir. Ayrıca, çerçeve kayıt ve sabit yığın ayırma alanları bilgilerindeki birincil aynı değerlere sahip olmalıdır.|

- **Giriş boyutu**

   İşlev giriş bayt cinsinden uzunluğu.

- **Geriye doğru izleme kodları sayısı**

   Geriye doğru izleme kodları dizideki sayısıdır. Bazı kodları (örneğin, UWOP_SAVE_NONVOL) geriye doğru izleme Not dizideki birden fazla yuvası gerektirir.

- **Çerçeve kaydı**

   Sıfır olmayan, ardından çerçeve işaretçisi işlevi kullanır ve bu alan UNWIND_CODE düğümleri işlemi bilgileri alan için aynı kodlama kullanılarak çerçeve işaretçisi olarak kullanılan kalıcı kayıt sayısıdır.

- **Çerçeve kaydı uzaklık (ölçeği Genişletilmiş)**

   Çerçeve kaydı alanın sıfır değilse, ardından oluşturulduğunda FP reg için uygulanan RSP ölçeklendirilmiş uzaklığı budur. Gerçek FP reg ayarlanır RSP + 16 \* 0 uzaklıkları 240 izin vererek, bu sayı. Bu, dinamik yığın çerçevesi, daha kısa yönergeleri (daha fazla yönerge 8-bit imzalı sapma formu kullanabilirsiniz) aracılığıyla daha iyi kod yoğunluğu izin vermek için yerel yığın ayırma ortasına FP reg işaret verir.

- **Bırakma kodları dizisi**

   Giriş etkisini kalıcı yazmaçlar ve RSP açıklayan bir dizi öğelerinin budur. Tek tek öğelerin anlamı UNWIND_CODE üzerinde bakın. Hizalama amacıyla bu dizinin her zaman (Bu durumda dizi bir geriye doğru izleme kodları alan sayısı tarafından belirtilenden uzun olacaktır) sayıda olabilecek kullanılmayan son giriş girişe sahip olur.

- **Özel durum işleyicisinin adresi**

   Bu işlevin dile özgü özel durum/sonlandırma işleyicisi bir görüntü göreli işaretçisi (UNW_FLAG_CHAININFO bayrağı açık olması ve UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayrakları birine ayarlanır) olur.

- **Dile özel işleyici veri**

   Bu işlevin dile özgü özel durum işleyicisi verilerdir. Bu verilerin biçimi belirtilmemiş ve tamamen kullanılan belirli bir özel durum işleyicisi tarafından belirlenir.

- **Zincirleme Bırakma bilgi**

   UNW_FLAG_CHAININFO bayrağı ayarlandıysa UNWIND_INFO yapısı üç UWORDs ile sona erer.  Bu UWORDs işlevi zincirleme RUNTIME_FUNCTION bilgilerini temsil eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)