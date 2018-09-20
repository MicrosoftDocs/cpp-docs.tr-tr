---
title: Param dizisi ve üç nokta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2caf6415fdbceb506b736e209c6e7e384b567c5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384383"
---
# <a name="param-array-and-ellipsis"></a>Param Dizisi ve Üç Nokta

Param dizisi, aşırı yüklenmiş işlev çağrılarını çözümlemek için önceliği, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Yönetilen Uzantılar ve yeni sözdizimi C# ve Visual Basic desteği param dizisi için açık desteği yoktur. Bunun yerine, bir sıradan dizi bir öznitelik ile şu şekilde bayraklar:

```
void Trace1( String* format, [ParamArray]Object* args[] );
void Trace2( String* format, Object* args[] );
```

Bu ikisi de aynı, Ara sırada `ParamArray` özniteliği etiketleri bu C# veya diğer CLR diller için bir dizi değişken sayıda her çağrıldığında öğelerle alma. Hangi bir örnek üç nokta bildirir olarak ayarlanmış bir aşırı yüklenmiş işlev çözüm programlarda yönetilen uzantıları ve yeni sözdiziminin arasındaki davranış değişikliği olduğunu ve ikinci bildirir bir `ParamArray` tarafından sağlanan aşağıdaki örnekteki gibi bir öznitelik Artur Laksberg.

```
int fx(...); // 1
int fx( [ParamArray] Int32[] ); // 2
```

Yönetilen Uzantılar'nokta öznitelik resmi bir dil durumuyla olmadığından şüphelenilebilir özniteliği öncelik verildi. Ancak, yeni sözdiziminde param dizisi doğrudan dil içinde artık desteklenmektedir ve daha güçlü yazıldığı için üç nokta üzerinde öncelik verilir. Bu nedenle, Yönetilen Uzantılar ' çağrısı

```
fx( 1, 2 );
```

çözümler `fx(...)` yeni söz ederken, bu çözümler `ParamArray` örneği. Program davranış'ınızı üç nokta örnek çağrıda, bağlı olma üzerinde `ParamArray`, imza veya çağrı değiştirmeniz gerekecektir.

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)