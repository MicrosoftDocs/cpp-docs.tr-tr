---
title: Derleyici Uyarısı (Düzey 2) C4275 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55b93d1ebd81850982b4f6ceac1ceb008ed1fa49
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890289"
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