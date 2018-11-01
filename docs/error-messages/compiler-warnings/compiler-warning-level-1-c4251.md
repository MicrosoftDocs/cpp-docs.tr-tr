---
title: Derleyici Uyarısı (düzey 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: d2fff1d2f30c4ac80af6d5b9ca452fa5f30f5a15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649663"
---
# <a name="compiler-warning-level-1-c4251"></a>Derleyici Uyarısı (düzey 1) C4251

'identifier': Sınıf 'type' sınıfı 'type2' istemcileri tarafından kullanılacak dll arabirimi olması gerekiyor

Bir sınıf ile dışarı aktarılırken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:

- Tüm statik verileri DLL'den dışa aktarılan işlevleri aracılığıyla erişimi var.

- Hiçbir satır içine alınmış yöntemleri sınıfının statik verileri değiştirebilir.

- Hiçbir satır içine alınmış bir yöntem sınıfınızın CRT işlevleri veya diğer kitaplık işlevleri statik veri kullanabilirsiniz (bkz [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) daha fazla bilgi için).

- Sınıfınızın yöntemlerin hiçbiri (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik veri farklar olduğu türlerini kullanabilirsiniz.

Sanal işlevler içeren bir sınıf tanımlar ve işlevleri bir DLL örneklemek için çağırabilirsiniz tanımlama ve türe ait nesneleri silme tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.

C4251 yoksayılan bir tür kitaplığı'nda C++ standart hata ayıklama yayın derleme türetme varsa (**/mtd**) ve derleyici hata iletisinin _Container_base için burada ifade eder.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```