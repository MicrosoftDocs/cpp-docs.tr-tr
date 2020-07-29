---
title: Çalışma Zamanı Türü Bilgileri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: b6d3652539572f094d0e7139e6672402341c956d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232241"
---
# <a name="run-time-type-information"></a>Çalışma Zamanı Türü Bilgileri

Çalışma zamanı türü bilgileri (RTTı), program yürütme sırasında bir nesne türünün belirlenmesine izin veren bir mekanizmadır. RTTı, sınıf kitaplıklarının birçok satıcısı bu işlevin kendilerini uyguladığı için C++ diline eklenmiştir. Bu, kitaplıklar arasındaki uyumsuzluklara neden oldu. Bu nedenle, dil düzeyinde çalışma zamanı tür bilgileri desteğinin gerekli olduğu belirgin hale gelmiştir.

Netliği sağlamak için RTTı 'nin bu tartışması, işaretçilerle neredeyse tamamen kısıtlıdır. Ancak, tartışılan kavramlar da başvurular için de geçerlidir.

Çalışma zamanı türü bilgileri için üç ana C++ dil öğesi vardır:

- [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.

   Polimorfik türlerin dönüştürülmesi için kullanılır.

- [TypeId](../cpp/typeid-operator.md) işleci.

   Bir nesnenin tam türünü belirlemek için kullanılır.

- [Type_info](../cpp/type-info-class.md) sınıfı.

   İşleci tarafından döndürülen tür bilgilerini tutmak için kullanılır **`typeid`** .

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)
