---
title: Derleyici Uyarısı (düzey 1) C4251
ms.date: 04/21/2020
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 9f261d3deb7f1cac8cd5c60b920e0be49bc8b7a6
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032336"
---
# <a name="compiler-warning-level-1-c4251"></a>Derleyici Uyarısı (düzey 1) C4251

> '*type*' : class '*type1*' sınıfı ' ' istemcileri tarafından kullanılmak üzere dll arabirimine sahip olması gerekir '*type2*'

## <a name="remarks"></a>Açıklamalar

[__declspec(dllexport)](../../cpp/dllexport-dllimport.md)olarak bildirilen bir sınıf dışa aktarırken veri bozulması olasılığını en aza indirmek için şunları emin olun:

- Tüm statik verilerinize DLL'den dışa aktarılan işlevler aracılığıyla erişilir.

- Sınıfınızın hiçbir çizgili yöntemi statik verileri değiştiremez.

- Sınıfınızın astarlı yöntemleri CRT işlevlerini veya statik verileri kullanan diğer kitaplık işlevlerini kullanmaz. Daha fazla bilgi için, [CrT nesnelerini DLL sınırları içinde geçen olası hatalara](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)bakın.

- EXE ve DLL'deki anlık verilerin statik veri farklılıklarına sahip olduğu türlerin hiçbir yöntemi (çizgili olsun veya olmasın) kullanamaz.

Bir DLL'den bir sınıf dışa aktarırken sorunları önleyebilirsiniz: Sınıfınızı sanal işlevlere sahip olarak tanımlayın ve türdeki nesneleri anlık olarak ve silmek için işlevler tanımlayın. Daha sonra sadece türünde sanal işlevleri arayabilirsiniz.

C4251, sınıfınız C++ Standart Kitaplığı'ndaki bir türden türetilmişse, hata ayıklama **(/MTd)** derlemesi `_Container_base`yayımlıyorsanız ve derleyici hata iletisinin ifade ettiği yerde yoksayılabilir.

## <a name="example"></a>Örnek

Bu örnek, 'den `VecWrapper` `std::vector`türetilen özel bir sınıf dışa dışa aktarma.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllexport) VecWrapper : vector<Node *> {};   // C4251
```
