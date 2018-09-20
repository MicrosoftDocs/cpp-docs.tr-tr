---
title: CLR dizisi bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c3de17bb293e10c4e1a2287ef12b934633b1fe21
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426464"
---
# <a name="declaration-of-a-clr-array"></a>CLR Dizisi Bildirimi

Bildirmek için sözdizimi, örnekleme ve yönetilen bir dizi başlatma Yönetilen Uzantılar'dan C++ için Visual C++ için değişti.

Yönetilen Uzantılar'CLR dizi nesnesinde bildirimi standart bir dizi bildiriminde'nın bir uzantısı olan bir `__gc` anahtar çiftiyle olduğu gibi büyük olasılıkla virgülle doldurulmuş boyutu dizi nesnesinin adını arasındaki yerleştirildiği Örnekler:

```
void PrintValues( Object* myArr __gc[]);
void PrintValues( int myArr __gc[,,]);
```

Bu, C++ Standart Kitaplığı'na benzer bir şablon benzeri bildirimi kullandığımız yeni sözdiziminde basitleştirilmiştir `vector` bildirimi. İlk parametre, öğe türü gösterir. İkinci parametre dizi boyutu belirtir (ile varsayılan değer olan 1 yalnızca birden çok boyutta gerektiren bir ikinci bağımsız değişkeni). Dizi nesnesi izleme işleyicisidir ve bu nedenle bir hat verilmelidir. Öğe türü de bir başvuru türü ise, aynı zamanda bir hat gerektirir. Örneğin, yukarıdaki örnekte Yeni sözdiziminde belirtildiğinde, şu şekilde görünür:

```
void PrintValues( array<Object^>^ myArr );
void PrintValues( array<int,3>^ myArr );
```

Bir başvuru türü bir nesne yerine izleme işleyicisi olduğundan, bir işlevin dönüş türü olarak CLR dizisi belirtmek mümkündür. (Buna karşılık, bunu bir işlevin dönüş türü olarak yerel bir dizi belirlemek mümkün değildir.) Bunun yapılması Yönetilen Uzantılar'sözdizimi anlaşılamayacak biraz. Örneğin:

```
Int32 f() [];
int GetArray() __gc[];
```

Visual C++'da bildirim çok daha kolaydır. Örneğin,

```
array<Int32>^ f();
array<int>^ GetArray();
```

Toplu başlatma yerel ve yönetilen bir dizinin her iki dil sürümlerinde desteklenir. Örneğin:

```
int GetArray() __gc[] {
   int a1 __gc[] = { 1, 2, 3, 4, 5 };
   Object* myObjArray __gc[] = {
      __box(26), __box(27), __box(28), __box(29), __box(30)
   };
   return a1;
}
```

Yeni sözdiziminde önemli ölçüde basitleştirilmiştir (Yeni sözdiziminde, örtük kutulama olduğundan `__box` işleci ortadan - bkz [değer türleri ve Their davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md) bir tartışma için):

```
array<int>^ GetArray() {
   array<int>^ a1 = {1,2,3,4,5};
   array<Object^>^ myObjArray = {26,27,28,29,30};
   return a1;
}
```

Bir dizi bir CLR başvuru türü olduğundan, her bir dizi nesnesi izleme işleyicisi bildirimidir. Bu nedenle, dizi nesnelerini CLR yığında ayrılmış olmalıdır. (Yönetilen yığın ayırma adlarıyla gizler.) Yönetilen Uzantılar altında bir dizi nesne başlatma açık formu şöyledir:

```
Object* myArray[] = new Object*[2];
String* myMat[,] = new String*[4,4];
```

Yeni sözdiziminde `new` ifade ile değiştirilir `gcnew`. Boyut boyutları için parametre olarak geçirilen `gcnew` aşağıdaki gibi bir ifade:

```
array<Object^>^ myArray = gcnew array<Object^>(2);
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);
```

Yeni sözdiziminde, bir açık başlatma listesi izleyebilirsiniz `gcnew` ifadesi; bu Yönetilen Uzantılar'desteklenmiyor. Örneğin:

```
// explicit initialization list following gcnew
// was not supported in Managed Extensions
array<Object^>^ myArray =
   gcnew array<Object^>(4){ 1, 1, 2, 3 };
```

## <a name="see-also"></a>Ayrıca Bkz.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Diziler](../windows/arrays-cpp-component-extensions.md)