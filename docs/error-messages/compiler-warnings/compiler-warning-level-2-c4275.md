---
title: Derleyici Uyarısı (Düzey 2) C4275
ms.date: 11/04/2016
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 985a622e2c89306c453ae6c860d21e6265d0fff1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594330"
---
# <a name="compiler-warning-level-2-c4275"></a>Derleyici Uyarısı (Düzey 2) C4275

olmayan - DLL arabirimi classkey 'identifier' temel olarak kullanılan DLL arabirimi classkey 'tanımlayıcısı'

Dışarı aktarılan bir sınıf değil dışarı aktarılan bir sınıftan türetilmiş.

Bir sınıf ile dışarı aktarılırken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:

- Tüm statik verileri DLL'den dışa aktarılan işlevleri aracılığıyla erişilen.

- Hiçbir satır içine alınmış yöntemleri sınıfının statik verileri değiştirebilir.

- Hiçbir satır içine alınmış bir yöntem sınıfınızın CRT işlevleri veya statik veri diğer kitaplık işlevleri kullanın.

- Hiçbir satır içine alınmış sınıf işlevleri, örneğin, statik verilere eriştiği CRT işlevleri veya diğer kitaplık işlevleri kullanın.

- Sınıfınızın yöntemlerin hiçbiri (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik veri farklar olduğu türlerini kullanabilirsiniz.

Sanal işlevler içeren bir sınıf tanımlar ve işlevleri bir DLL örneklemek için çağırabilirsiniz tanımlama ve türe ait nesneleri silme tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.

C4275 yoksayılan Visual c++'ta, bir tür kitaplığı'nda C++ standart hata ayıklama yayın derleme türetme (**/mtd**) ve derleyici hata iletisinin _Container_base için burada ifade eder.

```
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```