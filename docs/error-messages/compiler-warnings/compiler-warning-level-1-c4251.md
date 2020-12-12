---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4251'
title: Derleyici Uyarısı (düzey 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 4d08462442fd64ebef85573f5d538d6a884c8131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266240"
---
# <a name="compiler-warning-level-1-c4251"></a>Derleyici Uyarısı (düzey 1) C4251

> '*Type*': '*Type1*' sınıfının '*type2*' sınıfının istemcileri tarafından kullanılabilmesi için dll arabirimi olması gerekir

## <a name="remarks"></a>Açıklamalar

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)olarak belirtilen bir sınıfı dışarı aktarırken veri bozulması olasılığını en aza indirmek için şunları doğrulayın:

- Tüm statik verilerinize DLL 'den aktarılmış işlevlerle erişilir.

- Sınıfınıza ait satır içine alınmış Yöntem, statik verileri değiştirebilir.

- Sınıfınızın satır içine alınmış yöntemleri, CRT işlevleri veya statik veri kullanan diğer kitaplık işlevlerini kullanmaz. Daha fazla bilgi için bkz. [CRT NESNELERINI DLL sınırları genelinde geçirme olası hataları](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md).

- Sınıfınızın bir yöntemi (satır içine alınmış veya olmayan), EXE ve DLL içindeki örneklemede statik veri farklılıkları bulunan türleri kullanabilir.

Bir DLL 'den bir sınıfı dışarı aktarırken oluşabilecek sorunlardan kaçınmak için: sınıfınızı sanal işlevlere sahip olacak şekilde tanımlayın ve tür nesneleri örneklendirilecek ve silebilirsiniz. Böylece, yalnızca türündeki sanal işlevleri çağırabilirsiniz.

Sınıfınız C++ standart kitaplığı 'ndaki bir türden türetildiyse, bir hata ayıklama sürümü (**/MTD**) derlediğiniz ve derleyici hata iletisinin başvurduğu durumlarda C4251 yoksayılabilir `_Container_base` .

## <a name="example"></a>Örnek

Bu örnek, öğesinden türetilmiş özel bir sınıfı dışarı aktarır `VecWrapper` `std::vector` .

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
