---
title: Yapı UNWIND_CODE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1da6f078741c598099e71da9164f54b56da3f355
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726654"
---
# <a name="struct-unwindcode"></a>struct UNWIND_CODE

Geriye doğru izleme kodu dizi işlemlerin sırasını RSP ve kalıcı kayıtlar etkileyen giriş bölümünde kaydetmek için kullanılır. Her kod öğesi biçimi aşağıdaki gibidir:

|||
|-|-|
|UBYTE|Uzaklık içinde giriş|
|UBYTE: 4|Bırakma işlemi kodu|
|UBYTE: 4|İşlem bilgileri|

Dizi giriş uzaklığı azalan göre sıralanır.

## <a name="offset-in-prolog"></a>Uzaklık içinde giriş

Yönergenin bitiminden giriş başından uzaklığı, 1 (diğer bir deyişle, sonraki yönergesi başlangıç uzaklığını) yanı sıra bu işlemi gerçekleştirir.

## <a name="unwind-operation-code"></a>Bırakma işlemi kodu

Not: Bazı işlem kodlarını yerel yığın çerçevesi bir değeri işaretsiz bir uzaklık gerektirir. Bu uzaklık başlangıcından sabit yığın ayırma (en düşük adres) bağlıdır. Çerçeve kaydı alanı UNWIND_INFO sıfırsa bu uzaklık RSP dayalıdır. Çerçeve kaydı alanın sıfır değilse, FP reg oluşturulduğunda RSP bulunduğu gelen uzaklık budur. Bu dp reg FP reg uzaklığı eksi eşittir (16 \* ölçeklendirilmiş çerçeve UNWIND_INFO öğesinde uzaklık kaydı). Ardından bir dp reg kullanılıyorsa FP reg giriş bölümünde kurulduktan sonra bir uzaklık alma herhangi bir geriye doğru izleme kodu yalnızca kullanılmalıdır.

Tüm işlem için `UWOP_SAVE_XMM128` ve `UWOP_SAVE_XMM128_FAR`uzaklık her zaman 8'in katı olur, çünkü tüm yığın değerlerini gösteren öğelerdir (yığın, her zaman 16 bayt hizalı) 8 baytlık sınırlardaki depolanır. Kısa bir uzaklık (küçüktür, 512 K) alır işlem kodları için bu kod için düğümleri son USHORT 8 ile bölünen uzaklığı tutar. İşlem kodları, uzun bir uzaklık alır (512K < = < 4 GB uzaklık), bu kod için son iki USHORT düğüm uzaklık (küçük endian biçiminde) tutun.

İşlem için `UWOP_SAVE_XMM128` ve `UWOP_SAVE_XMM128_FAR`, tüm 128-bit XMM işlemleri 16 bayt hizalı bellek üzerinde gerçekleşmesi gerektiği uzaklık her zaman 16, katları olmalıdır. Bu nedenle, bir ölçek faktörü 16 için kullanılan `UWOP_SAVE_XMM128`, 1 milyondan az uzaklıklarını erişimine izin verme.

Geriye doğru izlemeyi işlem kodu aşağıdakilerden biridir:

`UWOP_PUSH_NONVOL` (0) 1 düğüm

Kalıcı tamsayı kaydını, azaltma RSP 8 tarafından gönderin. İşlem bilgisi kayıt sayısıdır. Sonuç, kısıtlamalar nedeniyle unutmayın `UWOP_PUSH_NONVOL` geriye doğru izleme kodları ilk giriş bölümünde görünür ve gelenlere, geriye doğru izleme kodu dizideki en son gerekir. Bu göreli sıralamasını diğer tüm geriye doğru izleme kodları uygular. `UWOP_PUSH_MACHFRAME`.

`UWOP_ALLOC_LARGE` (1) 2 veya 3 düğüm

Yığın üzerinde büyük ölçekli bir alan ayırın. İki biçimi vardır. İşlem bilgisi 0 ve ardından bölü ayırma boyutu eşitse 8 512 K - 8 adede kadar bir ayırma izin İleri yuvasında kaydedilir. İşlem bilgisi eşittir 1 sonra ayırma ölçeklendirilmemiş boyutunu sonraki iki yuvaları ayırmaya olanak vererek little endian biçiminde kaydedilir en fazla 4GB - 8.

`UWOP_ALLOC_SMALL` (2) 1 düğüm

Yığın üzerinde küçük ölçekli bir alan ayırın. Ayırmanın boyutu işlemi bilgileri alandır \* 8 + 8, 8 ayırma 128 bayt izin verme.

Geriye doğru izleme kodu yığın ayırma için her zaman en kısa olası kodlamayı kullanmanız gerekir:

|**Ayırma boyutu**|**Kod geriye doğru izleme**|
|-|-|
|8 ile 128 bayt|`UWOP_ALLOC_SMALL`|
|136 için 512K - 8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 0|
|512K için 4G - 8 bayt|`UWOP_ALLOC_LARGE`, işlem bilgisi = 1|

`UWOP_SET_FPREG` (3) 1 düğüm

Bazı geçerli RSP uzaklığı için kayıt ayarlayarak çerçeve işaretçisi kaydı oluşturun. Uzaklık içinde UNWIND_INFO çerçeve kaydı uzaklık (Genişletilmiş) alanına eşittir \* 16, uzaklık 0 ile 240 izin verme. Bir uzaklık kullanımına kod yoğunluklu kısa yönerge formları kullanarak daha fazla erişim sağlayarak yardımcı sabit yığın ayırma ortasını işaret eden bir çerçeve işaretçisini oluşturma izin verir. İşlem bilgisi alanının ayrılmıştır ve kullanılmamalıdır unutmayın.

`UWOP_SAVE_NONVOL` (4) 2 düğüm

Kalıcı tamsayı kaydını MOV yerine bir anında İLETME kullanarak tasarruf edin. Bu birincil olarak sabit, önceden ayrılmış olan bir konumda yığınına bir kayıt kaydedildiği kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeği genişletilmiş-8 yığın olarak uzaklık sonraki kaydedilen işlem kodu yuvası Not yukarıda açıklandığı gibi geriye doğru izleme.

`UWOP_SAVE_NONVOL_FAR` (5) 3 düğüm

Kalıcı tamsayı kaydını yığın MOV yerine PUSH kullanılarak mesafesi ile tasarruf edin. Bu birincil olarak sabit, önceden ayrılmış olan bir konumda yığınına bir kayıt kaydedildiği kullanılır. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın uzaklığı sonraki kaydedilir Not yukarıda açıklandığı gibi iki işlem kodu yuvaları bırakma.

`UWOP_SAVE_XMM128` (8) 2 düğüm

Tüm 128 bit XMM kaydının yığında kaydedin. İşlem bilgisi kayıt sayısıdır. Ölçeği genişletilmiş-16 yığın olarak uzaklık sonraki yuvaya kaydedilir.

`UWOP_SAVE_XMM128_FAR` (9) 3 düğüm

Tüm 128 bit XMM kaydının yığın mesafesi ile tasarruf edin. İşlem bilgisi kayıt sayısıdır. Ölçeklendirilmemiş yığın uzaklığı, sonraki iki yuvada da kaydedilir.

`UWOP_PUSH_MACHFRAME` (10) 1 düğüm

Makine çerçeve gönderin.  Bu, bir donanım kesme veya özel durum etkisini kaydetmek için kullanılır. İki biçimi vardır. İşlem bilgisi 0 eşitse, aşağıdaki yığına:

|||
|-|-|
|RSP + 32|SS|
|RSP + 24|Eski RSP|
|RSP + 16|EFLAGS|
|RSP + 8|CS|
|RSP|KOPYALAMA|

Aşağıdaki bunun yerine gönderilen sonra işlem bilgisi, 1 değerine eşitse:

|||
|-|-|
|RSP + 40|SS|
|RSP + 32|Eski RSP|
|RSP + 24|EFLAGS|
|RSP + 16|CS|
|RSP + 8|KOPYALAMA|
|RSP|Hata kodu|

Bu geriye doğru izleme kodu asla gerçekten yürütülür ancak bunun yerine bir kesme yordamı gerçek giriş noktasından önce görünür ve yalnızca bir makine çerçevenin gönderme benzetimi için bir yer sağlamak için var olan bir kukla giriş bölümünde her zaman görünür. `UWOP_PUSH_MACHFRAME` Makine kavramsal olarak aşağıdaki yapmış gösteren benzetimi kaydeder:

1. RIP dönüş adresi yığının en üstünden pop *Temp*

2. Anında iletme SS

3. Eski RSP anında iletme

4. EFLAGS Gönder

5. Anında iletme CS

6. Anında iletme *Temp*

7. Hata kodu (op bilgisi 1 değerine eşitse) anında iletme

Benzetim `UWOP_PUSH_MACHFRAME` 40 işlemi azaltır RSP (op bilgisi 0 değerine eşittir) veya 48 (op bilgisi eşittir 1).

## <a name="operation-info"></a>İşlem bilgileri

Bu 4 BITS anlamını işlem koduna bağlıdır. Genel amaçlı (tamsayı) kaydı kodlamak için aşağıdaki eşlemeyi kullanılır:

|||
|-|-|
|0|RAX'DAKİ|
|1.|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSI|
|7|RDI|
|8-15|R8 R15 kayıtları için|

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)