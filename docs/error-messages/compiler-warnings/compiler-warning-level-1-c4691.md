---
title: Derleyici Uyarısı (düzey 1) C4691 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4691
dev_langs:
- C++
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca063d61b799a10bd1d629fdba1293e0a66b0752
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095124"
---
# <a name="compiler-warning-level-1-c4691"></a>Derleyici Uyarısı (düzey 1) C4691

'type': başvurulan tür, başvurulmayan derlemede 'file', bunun yerine geçerli çeviri biriminde tanımlanan tür bekleniyordu

Özgün tür tanımını içeren meta veri dosyası başvurulmayan ve derleyici bir yerel tür tanımı kullanıyor.

Burada yeniden durumda *dosya*, C4691 göz ardı veya pragma ile kapalı [uyarı](../../preprocessor/warning.md).  Diğer bir deyişle, oluşturmakta olduğunuz dosya nerede derleyicinin tür tanımı bulmayı beklediği dosya ile aynı olduğunda, C4691 yoksayabilirsiniz.

Ancak, aynı derlemesinden meta verilerinde başvurulan değil bir tanımı derleyici kullanıyorsa, beklenmeyen davranış oluşabilir; CLR türleri yalnızca tür adıyla, aynı zamanda derleme tarafından yazılmış.  Diğer bir deyişle, derleme z.dll bir türden Z derleme y.dll bir türden Z farklıdır.

## <a name="example"></a>Örnek

Bu örnek, özgün tür tanımı içerir.

```
// C4691_a.cpp
// compile with: /clr /LD /W1
public ref class Original_Type {};
```

## <a name="example"></a>Örnek

Bu örnek C4691_a.dll başvuruyor ve Original_Type türünde bir alan bildirir.

```
// C4691_b.cpp
// compile with: /clr /LD
#using "C4691_a.dll"
public ref class Client {
public:
   Original_Type^ ot;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4691 oluşturur.  Bu örnek için Original_Type bir tanım içeriyor ve C4691a.dll başvuruda bulunmamaya dikkat edin.

Çözmek için özgün türü tanımını içeren meta veri dosyası başvurusu ve yerel bildirimi ve tanımı kaldırın.

```
// C4691_c.cpp
// compile with: /clr /LD /W1
// C4691 expected

// Uncomment the following line to resolve.
// #using "C4691_a.dll"
#using "C4691_b.dll"

// Delete the following line to resolve.
ref class Original_Type;

public ref class MyClass : Client {};
```