---
title: CRT Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
ms.openlocfilehash: 980d94b29d31d8eea910fbdb171a0ae8df1dccca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344615"
---
# <a name="crt-initialization"></a>CRT Başlatma

Bu konu, CRT genel durumlarını yerel kodda nasıl başlatır açıklar.

Varsayılan olarak, bağlayıcı kendi başlatma kodunu sağlayan CRT kitaplığı içerir. Bu başlangıç kodu CRT kitaplığı başlatır, genel başlatıcıların çağırır ve daha sonra kullanıcı tarafından sağlanan çağırır `main` işlevi konsol uygulamaları için.

## <a name="initializing-a-global-object"></a>Genel nesne başlatma

Aşağıdaki kodu göz önünde bulundurun:

```
int func(void)
{
    return 3;
}

int gi = func();

int main()
{
    return gi;
}
```

C/C++ standardına göre `func()` önce çağrılmalıdır `main()` yürütülür. Ancak, kimin çağırdığı?

Bu, bir kesme noktası ayarlamak için belirlemek için tek yönlü `func()`, uygulamada hata ayıklamak ve yığın inceleyin. CRT kaynak kodu Visual Studio'da mümkün olmasıdır.

Yığını üzerindeki işlevlerin göz attığınızda, CRT işlev işaretçileri bir listesi üzerinden döngü ve bunları gibi her birini çağırma bulabilirsiniz. Bu işlevler ötekisi benzer `func()` veya sınıf örnekleri için oluşturucu.

CRT Visual C++ Derleyici işlev işaretçileri listesini alır. Derleyici, genel bir başlatıcı gördüğünde, dinamik bir başlatıcısında oluşturur. `.CRT$XCU` bölümü (burada `CRT` bölüm adı olduğu ve `XCU` grup adı). Komutu çalıştırın. Bu dinamik başlatıcılar listesi elde etmek için **dumpbin/all main.obj**ve ardından arama `.CRT$XCU` bölümünde (Main.cpp olarak C++ dosyası, C dosyası derlendiğinde). Aşağıdakine benzer olacaktır:

```
SECTION HEADER #6
.CRT$XCU name
       0 physical address
       0 virtual address
       4 size of raw data
     1F2 file pointer to raw data (000001F2 to 000001F5)
     1F6 file pointer to relocation table
       0 file pointer to line numbers
       1 number of relocations
       0 number of line numbers
40300040 flags
         Initialized Data
         4 byte align
         Read Only

RAW DATA #6
  00000000: 00 00 00 00                                      ....

RELOCATIONS #6
                                                Symbol    Symbol
Offset    Type              Applied To         Index     Name
--------  ----------------  -----------------  --------  ------
00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))
```

CRT iki işaretçi tanımlar:

- `__xc_a` İçinde `.CRT$XCA`

- `__xc_z` İçinde `.CRT$XCZ`

Her ikisinde dışında tanımlanan sembolleri olmayan `__xc_a` ve `__xc_z`.

Şimdi ne zaman bağlayıcı okur çeşitli `.CRT` grupları, bunları bir bölümü birleştirir ve alfabetik olarak sıralar. Buna kullanıcı tanımlı genel başlatıcıları (Visual C++ derleyicisi getirecek `.CRT$XCU`) her zaman sonra gelecektir `.CRT$XCA` ve önce `.CRT$XCZ`.

Bölüm şuna benzer:

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

Bu nedenle, CRT Kitaplığı hem de kullandığı `__xc_a` ve `__xc_z` başlangıç ve bitiş genel başlatıcıların listesinin, bunlar düzenlenir bellekte resmi yüklendikten sonra şekli nedeniyle belirlemek için.

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
