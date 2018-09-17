---
title: Dönüş değerleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673853417ad3dd5f08171ea2d5b55df5440705ad
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714644"
---
# <a name="return-values-c"></a>Dönüş Değerleri (C++)

64 bit'e sığabilen skaler bir dönüş değeri dahil RAX üzerinden döndürülür — bu m64 türleri içerir. Float, double ve vektör türleri gibi dahil olmayan skaler türleri [__m128](../cpp/m128.md), [__m128i](../cpp/m128i.md), [__m128d](../cpp/m128d.md) XMM0'da döndürülür. Kullanılmayan RAX'daki veya XMM0 döndürülen değerdeki bitler durumu tanımsızdır.

Kullanıcı tanımlı türler genel işlevleri ve statik üye işlevleri, değere göre döndürülebilir. RAX'daki değer döndürülmesi için kullanıcı tanımlı türler 1, 2, 4, 8, 16, 32 veya 64 bit uzunluğu olmalıdır; hiçbir kullanıcı tanımlı Oluşturucu, yok Edicisi veya kopya atama işleci; hiçbir özel veya korumalı statik olmayan veri üyesi; hiçbir başvuru türü statik olmayan veri üyesi; temel olmayan sınıflar; sanal işlev yok; ve ayrıca bu gereksinimleri karşılamayan veri üye yok. (Bu aslında C ++ 03 tanımı, POD türü. C ++ 11'de standart tanımı değiştiğinden, kullanılması önerilmez `std::is_pod` bu test için.) Aksi takdirde, arayanın bellek ayırma ve işaretçi dönüş değeri için ilk bağımsız değişken olarak geçirme sorumluluğu üstlenir. İzleyen bağımsız değişkenler, tek bir bağımsız değişken sağa doğru kayar. Aynı işaretçi RAX'daki Aranan tarafından iade edilmesi gerekir.

Bu örnekler, parametreler ve dönüş değerleri için işlevleri belirtilen bildirimleri ile nasıl geçirilir gösterir:

## <a name="example-of-return-value-1---64-bit-result"></a>Dönüş değeri 1-64 bit sonuç örneği

```Output
__int64 func1(int a, float b, int c, int d, int e);
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,
// callee returns __int64 result in RAX.
```

## <a name="example-of-return-value-2---128-bit-result"></a>Dönüş değeri 2-128 bit sonuç örneği

```Output
__m128 func2(float a, double b, int c, __m64 d);
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,
// callee returns __m128 result in XMM0.
```

## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>Dönüş değeri 3 - işaretçi tarafından kullanıcı türü sonuç örneği

```Output
struct Struct1 {
   int j, k, l;    // Struct1 exceeds 64 bits.
};
Struct1 func3(int a, double b, int c, float d);
// Caller allocates memory for Struct1 returned and passes pointer in RCX,
// a in RDX, b in XMM2, c in R9, d pushed on the stack;
// callee returns pointer to Struct1 result in RAX.
```

## <a name="example-of-return-value-4---user-type-result-by-value"></a>Dönüş değeri 4 - değere göre kullanıcı türü sonuç örneği

```Output
struct Struct2 {
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.
};
Struct2 func4(int a, double b, int c, float d);
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;
// callee returns Struct2 result by value in RAX.
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)