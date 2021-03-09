---
title: CRT Başlatma
description: CRT 'ın yerel koddaki genel durumu nasıl kullandığını açıklar.
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
ms.openlocfilehash: e33429d63cebb34514918d059649679ed28b924c
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514648"
---
# <a name="crt-initialization"></a>CRT Başlatma

Bu konu başlığı altında, CRT 'nin yerel koddaki genel durumu nasıl oluşturulduğu açıklanmaktadır.

Varsayılan olarak bağlayıcı, kendi başlangıç kodunu sağlayan CRT kitaplığını içerir. Bu başlangıç kodu CRT kitaplığını başlatır, genel başlatıcıları çağırır ve sonra `main` konsol uygulamaları için Kullanıcı tarafından sağlanmış işlevi çağırır.

## <a name="initializing-a-global-object"></a>Genel nesne başlatma

Aşağıdaki kodu inceleyin:

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

C/C++ standardına göre, `func()` yürütülmeden önce çağrılmalıdır `main()` . Ancak kim bunu çağırıyor?

Arayanın belirlenmesi için bir yol, içinde bir kesme noktası ayarlamak `func()` , uygulamada hata ayıklamak ve yığını incelemek. Bu, CRT kaynak kodu Visual Studio 'Ya dahil edildiğinden mümkündür.

Yığındaki işlevlere gözattığınızda, CRT 'nin işlev işaretçilerinin bir listesini çağırıyor olduğunu görürsünüz. Bu işlevler `func()` , veya sınıf örnekleri için oluşturuculara benzerdir.

CRT, Microsoft C++ derleyicisinden işlev işaretçilerinin listesini alır. Derleyici küresel bir başlatıcı gördüğünde, bölüm `.CRT$XCU` `CRT` adı olan ve grup adı olan bölümünde dinamik bir başlatıcı oluşturur `XCU` . Dinamik başlatıcıların listesini almak için, **dumpbin/All Main. obj** komutunu çalıştırın ve ardından bölümünde arama yapın `.CRT$XCU` . Bu, Main. cpp C dosyası değil bir C++ dosyası olarak derlendiğinde geçerlidir. Aşağıdaki örneğe benzer olacaktır:

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
--------  ----------------  -----------------  --------  -------
00000000  DIR32             00000000           C         ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))
```

CRT iki işaretçileri tanımlar:

- `.CRT$XCA` içinde `__xc_a`

- `.CRT$XCZ` içinde `__xc_z`

Hiçbir grup, ve dışında tanımlanmış başka bir sembol içermez `__xc_a` `__xc_z` .

Artık bağlayıcı çeşitli grupları okuduğunda `.CRT` , bunları bir bölümde birleştirir ve alfabetik olarak sıralar. Bu, Kullanıcı tanımlı genel başlatıcıların (Microsoft C++ derleyicisinin içine koyduğu `.CRT$XCU` ) her zaman `.CRT$XCA` ve daha önce geldiği anlamına gelir `.CRT$XCZ` .

Bu bölüm aşağıdaki örneğe benzeyecektir:

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

Bu nedenle, CRT kitaplığı, `__xc_a` görüntü yüklendikten `__xc_z` sonra bellekte yerleştirilme yöntemi nedeniyle genel başlatıcılar listesinin başlangıcını ve bitişini belirlemede, her ikisini de kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
