---
title: x64 giriş ve bitiş bölümü
ms.date: 12/17/2018
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
ms.openlocfilehash: d0b7444af6e434a09f6af5f5b1c144b46c79ad56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328441"
---
# <a name="x64-prolog-and-epilog"></a>x64 giriş ve bitiş bölümü

Yığın alanını ayıran, diğer işlevleri çağıran, geçici olmayan kayıtları kaydeden veya özel durum işleme kullanan her işlev, ilgili işlev tablosu girişiyle ilişkili gevşeme verilerinde adres sınırları açıklanan bir prolog'a sahip olmalıdır. Daha fazla bilgi için [bkz.](../build/exception-handling-x64.md) Prolog, gerekirse bağımsız değişken kayıtlarını ev adreslerine kaydeder, yığındaki geçici olmayan kayıtları iter, yığının sabit kısmını yerel halk ve geçici ler için ayırır ve isteğe bağlı olarak bir çerçeve işaretçisi oluşturur. İlişkili gevşeme verileri prolog'un eylemini açıklamalı ve prolog kodunun etkisini geri almak için gerekli bilgileri sağlamalıdır.

Yığındaki sabit ayırma birden fazla sayfaysa (yani 4096 bayttan büyükse), yığın ayırmanın birden fazla sanal bellek sayfasına yayılabilir ve bu nedenle ayırmanın ayrılmadan önce denetlenmesi gerekir. Prolog'dan çağrılabilen ve bağımsız değişken kayıtlarının hiçbirini yok etmeyen özel bir yordam bu amaç için sağlanır.

Geçici olmayan kayıtları kaydetmek için tercih edilen yöntem, sabit yığın ayırmadan önce bunları yığına taşımaktır. Sabit yığın ayırma, geçici olmayan kayıtlar kaydedilmeden önce gerçekleştirilirse, kaydedilen kayıt alanını ele almak için büyük olasılıkla 32 bitlik bir yer değiştirme gerekir. (Bildirildiğine göre, kayıt itmeler hamle kadar hızlı ve itmeler arasında zımni bağımlılık rağmen öngörülebilir bir gelecek için öyle kalmalıdır.) Geçici olmayan kayıtlar herhangi bir sırada kaydedilebilir. Ancak, prolog'daki geçici olmayan bir kaydın ilk kullanımı onu kaydetmek olmalıdır.

## <a name="prolog-code"></a>Prolog kodu

Tipik bir prolog için kod olabilir:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    sub    RSP, fixed-allocation-size
    lea    R13, 128[RSP]
    ...
```

Bu prolog, bağımsız değişken kaydı RCX'i kendi evinde saklar, geçici olmayan kayıtları R13-R15'i kaydeder, yığın çerçevesinin sabit kısmını ayırır ve sabit ayırma alanına 128 bayt işaretleyen bir kare işaretçisi oluşturur. Ofset kullanmak, sabit ayırma alanının daha fazlasının tek tek ofset ile ele alınmasını sağlar.

Sabit ayırma boyutu bir bellek sayfasından büyük veya eşitse, RSP'yi değiştirmeden önce bir yardımcı işlev çağrılmalıdır. Bu yardımcı, `__chkstk`yığının düzgün uzatılmasını sağlamak için ayrılacak yığın aralığını deburtur. Bu durumda, önceki prolog örneği yerine olacaktır:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    mov    RAX,  fixed-allocation-size
    call   __chkstk
    sub    RSP, RAX
    lea    R13, 128[RSP]
    ...
```

Yardımcı, `__chkstk` R10, R11 ve koşul kodları dışında hiçbir kaydı değiştirmez. Özellikle, RAX'i değişmeden döndürecek ve tüm geçici olmayan kayıtları ve bağımsız değişken geçen kayıtları değiştirilmemiş olarak bırakır.

## <a name="epilog-code"></a>Epilog kodu

Bir işlevin her çıkışında epilog kodu bulunur. Normalde sadece bir prolog varken, birçok epilogs olabilir. Epilog kodu yığını sabit ayırma boyutuna (gerekirse) kırpar, sabit yığın ayırmayı bulur, kaydedilen değerlerini yığından çıkararak geçici olmayan kayıtları geri yüklenir ve döndürür.

Epilog kodu, özel durumlar ve kesintiler yoluyla güvenilir bir şekilde gevşemek için kodun gevşemesi için katı bir kural kümesine uymalıdır. Bu kurallar, her epilogu tanımlamak için ek veri gerekmedığından, gerekli gevşeme verisi miktarını azaltır. Bunun yerine, gevşeme kodu bir epilog tanımlamak için bir kod akışı üzerinden ileri tarama tarafından bir epilog yürütülmektedir belirleyebilirsiniz.

İşlevde çerçeve işaretçisi kullanılmazsa, epilog önce yığının sabit kısmını bulmalı, geçici olmayan kayıtlar atılırsa ve denetim çağrı işlevine döndürülür. Örneğin,

```MASM
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

İşlevde bir çerçeve işaretçisi kullanılıyorsa, yığın epilogun yürütülmesinden önce sabit ayırmasına kesilmelidir. Bu eylem teknik olarak epilog bir parçası değildir. Örneğin, daha önce kullanılan prolog geri almak için aşağıdaki epilog kullanılabilir:

```MASM
    lea      RSP, -128[R13]
    ; epilogue proper starts here
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

Uygulamada, bir kare işaretçisi kullanıldığında, RSP'yi iki adımda ayarlamak için iyi bir neden yoktur, bu nedenle bunun yerine aşağıdaki epilog kullanılır:

```MASM
    lea      RSP, fixed-allocation-size - 128[R13]
    pop      R13
    pop      R14
    pop      R15
    ret
```

Bu formlar bir epilog için sadece yasal olanlar. Bir `add RSP,constant` veya `lea RSP,constant[FPReg]`daha fazla 8 bayt lık bir dizi bir dizi veya `return` bir `jmp`veya daha fazla . (Yalnızca `jmp` bir deyim alt kümesine özette izin verilir. Alt küme, modrm `jmp` mod alan değerinin 00 olduğu ModRM bellek referansları içeren deyimler sınıfıdır. ModRM `jmp` mod alan değeri 01 veya 10 ile epilog ifadelerin kullanımı yasaktır. Amd x86-64 Mimarlık Programcısının Manuel Cilt 3:Genel Amaç ve Sistem Talimatları'nda, izin verilen ModRM referansları hakkında daha fazla bilgi için Tablo A-15'e bakın.) Başka hiçbir kod görüntülenemez. Özellikle, hiçbir şey bir özet içinde, bir iade değeri yükleme de dahil olmak üzere zamanlanabilir.

Bir çerçeve işaretçisi kullanılmadığında, `add RSP,constant` özet yığının sabit kısmını bulmak için üst sözlüğünü niçin kullanması gerekir. Bunun yerine `lea RSP,constant[RSP]` kullanmayabilir. Bu kısıtlama, durum özetlerini ararken tanıyacak daha az desene sahip olması için çözünme koduna sahiptir.

Bu kurallara göre, gevşeme kodu, bir epilogun şu anda yürütülmekte olduğunu belirlemesine ve arama işlevinin bağlamını yeniden oluşturmaya izin vermek için epilogun geri kalanının yürütülmesini simüle etmesine olanak tanır.

## <a name="see-also"></a>Ayrıca bkz.

[x64 Yazılım Sözleşmeleri](x64-software-conventions.md)
