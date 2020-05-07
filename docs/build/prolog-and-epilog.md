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

Yığın alanı ayıran, diğer işlevleri çağıran, kalıcı kayıtları kaydeden veya özel durum işlemenin kullanıldığı her işlev, adres sınırları ilgili işlev tablosu girdisiyle ilişkili geriye doğru izleme verilerinde açıklanan bir giriş içermelidir. Daha fazla bilgi için bkz. [x64 özel durum işleme](../build/exception-handling-x64.md). Giriş, bağımsız değişken yazmaçlarını giriş adreslerinde kaydeder, yığında kalıcı yazmaçları gönderir, Yereller ve geçiciler için yığının sabit bölümünü ayırır ve isteğe bağlı olarak bir çerçeve işaretçisi oluşturur. İlişkili geriye doğru izleme verileri, giriş kodunun etkisini anlamalıdır ve giriş kodunun etkisini geri almak için gereken bilgileri vermelidir.

Yığındaki sabit ayırma birden çok sayfadan fazlaysa (4096 bayttan fazla), yığın ayırma birden fazla sanal bellek sayfasına yayılabileceğinden, bu nedenle tahsisatın ayrılmadan önce denetlenmesi gerekir. Bu amaçla, giriş noktasından çağrılabilir olan ve bağımsız değişken yazmaçlarından hiçbirini yok eden özel bir yordam sağlanır.

Kalıcı kayıtları kaydetmek için tercih edilen yöntem, sabit yığın ayırmadan önce bunları yığına taşımadır. Kalıcı yazmaçları kaydedilmeden önce sabit yığın ayırma işlemi gerçekleştirilirse, kaydedilen kayıt alanını ele almak için büyük olasılıkla 32 bitlik bir öteleme gerekir. (Rapor, yazmaçların gönderimleri, taşınmalara kadar hızlı bir şekilde yapılır ve daha sonra artma ' de, gönderimler arasında kapsanan bağımlılıktan sorumlu olması için devam etmelidir.) Kalıcı yazmaçları herhangi bir sıraya kaydedilebilir. Ancak, giriş bölümünde kalıcı kaydın ilk kullanımı, kaydetmek için olmalıdır.

## <a name="prolog-code"></a>Giriş kodu

Tipik bir giriş için kod şu olabilir:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    sub    RSP, fixed-allocation-size
    lea    R13, 128[RSP]
    ...
```

Bu giriş, RCX bağımsız değişkenini kendi giriş konumunda depolar, kalıcı yazmaçları kaydeder R13-R15, yığın çerçevesinin sabit bölümünü ayırır ve sabit ayırma alanına 128 bayt işaret eden bir çerçeve işaretçisi oluşturur. Bir uzaklık kullanılması, sabit ayırma alanının daha fazlasına tek baytlık uzaklıklarla değinilmesine olanak tanır.

Sabit ayırma boyutu bir bellek sayfasından büyükse veya buna eşitse, RSP değiştirilmeden önce bir yardımcı işlev çağrılmalıdır. Bu yardımcı, `__chkstk`yığının düzgün şekilde genişletildiğinden emin olmak için, ayrılan yığın aralığını yoklamıştır. Bu durumda, önceki giriş örneği şöyle olacaktır:

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

`__chkstk` Yardımcı, R10, R11 ve koşul kodları dışındaki herhangi bir kaydı değiştirmeyecektir. Özellikle, KORX 'i değiştirmez ve tüm kalıcı yazmaçları ve bağımsız değişken geçirme kayıtlarını değiştirilmemiş olarak bırakır.

## <a name="epilog-code"></a>Bitiş kodu

Bitiş kodu bir işleve yapılan her çıkışta bulunur. Normalde yalnızca bir giriş olduğunda, çok sayıda epıte bulunabilir. Bitiş kodu, yığını sabit ayırma boyutuna kırpar (gerekliyse), sabit yığın ayırmayı serbest bırakır, kayıtlı değerlerini yığından ayırarak kalıcı kayıtları geri yükler ve döndürür.

Bitiş kodu, özel durumlar ve kesmeler aracılığıyla güvenilir bir şekilde geriye doğru geri dönmek için bırakma kodu için bir dizi kesin kural izlemelidir. Bu kurallar, her bir bitiş için ek veri gerekmediği için gereken geriye doğru veri miktarını azaltır. Bunun yerine, geri sarma kodu bir bitişin bir bitiş tanımlamak için bir kod akışından ileriye doğru tarama yaparak yürütüldüğünü tespit edebilir.

İşlevde hiçbir çerçeve işaretçisi kullanılmazsa, ilk olarak yığının sabit bölümünün serbest olması gerekir, kalıcı yazmaçları kaldırılır ve arama işlevine denetim döndürülür. Örneğin,

```MASM
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

İşlevde bir çerçeve işaretçisi kullanılıyorsa, yığın yürütmeden önce yığının sabit ayırmasına kırpılmalıdır. Bu eylem Teknik olarak bitiş 'nin bir parçası değildir. Örneğin, aşağıdaki bitiş, daha önce kullanılan girişi geri almak için kullanılabilir:

```MASM
    lea      RSP, -128[R13]
    ; epilogue proper starts here
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

Uygulamada, bir çerçeve işaretçisi kullanıldığında RSP 'yi iki adımda ayarlamak için iyi bir neden yoktur, bu nedenle bunun yerine aşağıdaki bitiş kullanılır:

```MASM
    lea      RSP, fixed-allocation-size - 128[R13]
    pop      R13
    pop      R14
    pop      R15
    ret
```

Bu formlar, bir bitiş için tek yasal olanlardır. Bir `add RSP,constant` veya `lea RSP,constant[FPReg]`' den, ardından sıfır veya daha fazla 8 baytlık yazmaç pop ve a `return` ya da bir `jmp`serisini içermelidir. (Yalnızca bir `jmp` deyim alt kümesi bitiş içinde izin verilebilir. Alt küme, ModRM mod alan `jmp` değerinin 00 olduğu ModRM bellek başvuruları olan deyimler sınıfına özel olarak eklenir. ModRM mod `jmp` alan değeri 01 veya 10 olan bitiş içindeki deyimlerin kullanımı yasaktır. İzin verilen ModRM başvuruları hakkında daha fazla bilgi için, bkz. AMD x86-64 mimari programcı 'nin El Ile birim 3: Genel Amaçlı ve sistem yönergeleri.) Başka kod görüntülenemez. Özellikle, bir dönüş değeri yüklemesi dahil olmak üzere bir bitiş içinde hiçbir şey zamanlanamaz.

Bir çerçeve işaretçisi kullanılmazsa, yığının sabit kısmını serbest bırakmak için bitiş `add RSP,constant` öğesini kullanmalıdır. `lea RSP,constant[RSP]` Bunun yerine kullanılamıyor olabilir. Bu kısıtlama, geri bırakma kodunun epılar aranırken daha az desen tanıması için vardır.

Bu kuralların ardından, geriye doğru yürütüldüğünü ve çağıran işlevin bağlamını yeniden oluşturmak için geri kalanı yürütmeye olanak tanımak üzere açılım kodunun Şu anda yürütülmekte olduğunu belirlemesini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[x64 yazılım kuralları](x64-software-conventions.md)
