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
ms.openlocfilehash: 195274d7bcef0ff4d82383a8ec828ca9267573b0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178944"
---
# <a name="run-time-type-information"></a>Çalışma Zamanı Türü Bilgileri

Çalışma zamanı türü bilgileri (RTTı), program yürütme sırasında bir nesne türünün belirlenmesine izin veren bir mekanizmadır. RTTı, C++ sınıf kitaplıklarının birçok satıcısı bu işlevin kendilerini uyguladığı için dile eklendi. Bu, kitaplıklar arasındaki uyumsuzluklara neden oldu. Bu nedenle, dil düzeyinde çalışma zamanı tür bilgileri desteğinin gerekli olduğu belirgin hale gelmiştir.

Netliği sağlamak için RTTı 'nin bu tartışması, işaretçilerle neredeyse tamamen kısıtlıdır. Ancak, tartışılan kavramlar da başvurular için de geçerlidir.

Çalışma zamanı türü bilgileri C++ için üç ana dil öğesi vardır:

- [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.

   Polimorfik türlerin dönüştürülmesi için kullanılır.

- [TypeId](../cpp/typeid-operator.md) işleci.

   Bir nesnenin tam türünü belirlemek için kullanılır.

- [Type_info](../cpp/type-info-class.md) sınıfı.

   **TypeId** işlecinin döndürdüğü tür bilgilerini tutmak için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)
