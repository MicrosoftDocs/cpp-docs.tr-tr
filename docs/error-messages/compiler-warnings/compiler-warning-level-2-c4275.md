---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4275'
title: Derleyici Uyarısı (düzey 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 0dd212d7439b73c28a5426574b72ff8150abe93c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173655"
---
# <a name="compiler-warning-level-2-c4275"></a>Derleyici Uyarısı (düzey 2) C4275

> '*class_1*' dll olmayan arabirim sınıfı, '*class_2*' dll arabirimi sınıfı için temel olarak kullanıldı

İçe aktarılmış bir sınıf, dışarıya aktarılmamış bir sınıftan türetildi.

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)ile bir sınıfı dışarı aktarırken veri bozulması olasılığını en aza indirmek için şunları yaptığınızdan emin olun:

- Tüm statik verilerinize DLL 'den aktarılmış işlevlerle erişilir.

- Sınıfınıza ait satır içine alınmış Yöntem, statik verileri değiştirebilir.

- Sınıfınızın satır içine alınmış yöntemleri, CRT işlevleri veya statik veri kullanan diğer kitaplık işlevlerini kullanmaz.

- Satır içine alınmış sınıf işlevleri CRT işlevleri veya statik verilere erişebileceğiniz diğer kitaplık işlevlerini kullanmaz.

- Sınıfınıza bakılmaksızın (satır taban larından bağımsız olarak), EXE ve DLL içindeki örneklemede statik veri farklılıkları bulunan türler kullanılabilir.

Sanal işlevler içeren bir sınıf tanımlayan bir DLL tanımlayarak ve türü nesneleri oluşturmak ve silmek için çağırabilmeniz gereken işlevleri belirleyerek sınıfları dışarı aktarmaya kaçınabilirsiniz.  Böylece, yalnızca türündeki sanal işlevleri çağırabilirsiniz.

C++ standart kitaplığındaki bir türden türetmeniz halinde C4275, bir hata ayıklama sürümü (**/MTD**) ve derleyici hata iletisinin başvurduğu bir türden türeterek Visual C++ yok sayılabilir `_Container_base` .

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```
