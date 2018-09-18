---
title: İfadelerdeki diziler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34f8a45dfa9de9a5a48e13cb6a38f667e5963f2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068552"
---
# <a name="arrays-in-expressions"></a>İfadelerdeki Diziler

Bir dizi türünde bir tanımlayıcısı göründüğünde bir ifadede dışında `sizeof`, adres (**&**), veya başlatma, bir başvurunun ilk dizi öğesinin işaretçisine dönüştürülür. Örneğin:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

`psz` işaretçisi `szError1` dizisinin ilk öğesine işaret eder. İşaretçilerin aksine, dizilerin değiştirilebilir I-değerleri olmadığına dikkat edin. Bu nedenle aşağıdaki atama geçersizdir:

```cpp
szError1 = psz;
```

## <a name="see-also"></a>Ayrıca bkz.

[Diziler](../cpp/arrays-cpp.md)