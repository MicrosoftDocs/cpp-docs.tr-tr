---
title: İfadelerdeki Diziler
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
ms.openlocfilehash: 0f2ef43c2a5bc4f8a44378c21d6d53b14f07ea07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184386"
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