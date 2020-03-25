---
title: Derleyici hatası C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 40156dfaad5965d30a32d3aa2ac574a5f91999ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176410"
---
# <a name="compiler-error-c3888"></a>Derleyici hatası C3888

' name ': Bu sabit değerli veri üyesiyle ilişkili const ifadesi/CLI tarafından C++desteklenmiyor

[Literal](../../extensions/literal-cpp-component-extensions.md) anahtar sözcüğüyle belirtilen *ad* veri üyesi derleyicinin desteklemediği bir değer ile başlatılır. Derleyici yalnızca sabit integral, Enum veya dize türlerini destekler. **C3888** hatasının olası nedeni, veri üyesinin bir bayt dizisiyle başlatılmasından kaynaklanıyor olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Belirtilen sabit değerli veri üyesinin desteklenen bir tür olup olmadığını denetleyin.

## <a name="see-also"></a>Ayrıca bkz.

[değişmez değer](../../extensions/literal-cpp-component-extensions.md)
