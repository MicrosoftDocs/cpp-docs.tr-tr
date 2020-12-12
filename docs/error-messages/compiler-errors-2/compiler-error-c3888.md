---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3888'
title: Derleyici hatası C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 5b47d78d0d6c75f4bdd266f95fff2ce4ab025d4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274326"
---
# <a name="compiler-error-c3888"></a>Derleyici hatası C3888

' name ': Bu sabit değerli veri üyesiyle ilişkili const ifadesi C++/CLı tarafından desteklenmiyor

[Literal](../../extensions/literal-cpp-component-extensions.md) anahtar sözcüğüyle belirtilen *ad* veri üyesi derleyicinin desteklemediği bir değer ile başlatılır. Derleyici yalnızca sabit integral, Enum veya dize türlerini destekler. **C3888** hatasının olası nedeni, veri üyesinin bir bayt dizisiyle başlatılmasından kaynaklanıyor olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Belirtilen sabit değerli veri üyesinin desteklenen bir tür olup olmadığını denetleyin.

## <a name="see-also"></a>Ayrıca bkz.

[ayarını](../../extensions/literal-cpp-component-extensions.md)
