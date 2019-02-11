---
title: Derleyici Uyarısı (Düzey 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 6e0e80d465d77bd4fe99fbcaa98e289b8a4c8b63
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987033"
---
# <a name="compiler-warning-level-2-c4275"></a>Derleyici Uyarısı (Düzey 2) C4275

> olmayan - DLL arabirimi sınıfının*class_1*'DLL arabirimi sınıfı için temel olarak kullanıldı'*class_2*'

Dışarı aktarılan bir sınıf türetilmiş bir sınıftan dışarı değildi.

Bir sınıf ile dışarı aktarılırken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:

- Tüm statik verileri DLL'den dışa aktarılan işlevleri aracılığıyla erişilen.

- Hiçbir satır içine alınmış yöntemleri sınıfının statik verileri değiştirebilir.

- Hiçbir satır içine alınmış bir yöntem sınıfınızın CRT işlevleri veya statik veri kullanan diğer kitaplık işlevleri kullanın.

- Hiçbir satır içine alınmış sınıf işlevleri, statik verilere eriştiği CRT işlevleri veya diğer kitaplık işlevleri kullanın.

- Sınıfınızın yöntemlerin hiçbiri (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik veri farklar olduğu türlerini kullanabilirsiniz.

Sanal işlevler içeren bir sınıf tanımlar ve işlevleri bir DLL örneklemek için çağırabilirsiniz tanımlama ve türe ait nesneleri silme tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.

C4275 yoksayılan Visual c++'ta, bir tür kitaplığı'nda C++ standart hata ayıklama yayın derleme türetme (**/mtd**) ve derleyici hata iletisini burada başvurduğu `_Container_base`.

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```