---
title: Derleyici Uyarısı (düzey 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: 8a723b7ce7fc79fb6be9c9dd2b500631098622b0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163225"
---
# <a name="compiler-warning-level-1-c4251"></a>Derleyici Uyarısı (düzey 1) C4251

' tanımlayıcı ': ' type2 ' sınıfının istemcileri tarafından kullanılabilmesi için ' Type ' sınıfının dll arabirimi olması gerekir

[__Declspec (dllexport)](../../cpp/dllexport-dllimport.md)ile bir sınıfı dışarı aktarırken veri bozulması olasılığını en aza indirmek için şunları doğrulayın:

- Tüm statik verileriniz DLL 'den aktarılmış işlevlerle erişir.

- Sınıfınıza ait satır içine alınmış Yöntem, statik verileri değiştirebilir.

- Sınıfınızın satır içine alınmış yöntemleri CRT işlevleri veya diğer kitaplık işlevleri, statik veri kullanır (daha fazla bilgi için bkz. daha fazla bilgi için bkz. [DLL sınırları genelınde CRT nesneleri geçirme olası hataları](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)

- Sınıfınıza bakılmaksızın (satır taban larından bağımsız olarak), EXE ve DLL içindeki örneklemede statik veri farklılıkları bulunan türler kullanılabilir.

Sanal işlevler içeren bir sınıf tanımlayan bir DLL tanımlayarak ve türü nesneleri oluşturmak ve silmek için çağırabilmeniz gereken işlevleri belirleyerek sınıfları dışarı aktarmaya kaçınabilirsiniz.  Böylece, yalnızca türündeki sanal işlevleri çağırabilirsiniz.

C++ Standart kitaplıktaki bir türden türetmeniz halinde C4251, hata ayıklama sürümü ( **/MTD**) ve derleyici hata iletisinin _Container_base başvurduğu durumlarda yok sayılabilir.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```
