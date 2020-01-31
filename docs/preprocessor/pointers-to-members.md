---
title: pointers_to_members pragması
ms.date: 08/29/2019
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 6058e3e4855eb745a01410e31eb9f454ef131ab1
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821414"
---
# <a name="pointers_to_members-pragma"></a>pointers_to_members pragması

**C++Belirli**

Sınıf üyesine yönelik işaretçinin, ilişkili sınıf tanımından önce bildirilip belirtimeyeceğini belirtir. İşaretçi boyutunu ve işaretçiyi yorumlamak için gerekli kodu denetlemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **#pragma pointers_to_members (** *işaretçi bildirimi* [ **,** *en-genel-temsili* ])

## <a name="remarks"></a>Açıklamalar

[/VMB veya/VMG](../build/reference/vmb-vmg-representation-method.md) derleyici seçeneklerini veya [Devralma anahtar sözcüklerini](../cpp/inheritance-keywords.md)kullanarak kaynak dosyanıza bir **pointers_to_members** pragma yerleştirebilirsiniz.

*İşaretçi bildirimi* bağımsız değişkeni, ilişkili işlev tanımından önce veya sonra bir üyeye işaretçi mi bildirmeyeceğinizi belirtir. *İşaretçi bildirimi* bağımsız değişkeni aşağıdaki iki simgeden biridir:

| Bağımsız Değişken | Açıklamalar |
|--------------|--------------|
| **full_generality** | Güvenli, bazen uygun durumda olmayan kod üretir. Üyenin herhangi bir işaretçisi ilişkili sınıf tanımından önce bildirilirse **full_generality** kullanırsınız. Bu bağımsız değişken her zaman *en genel gösterim* bağımsız değişkeni tarafından belirtilen işaretçi gösterimini kullanır. /vmg ile eşdeğerdir. |
| **best_case** | Tüm üye işaretçileri için best-case gösterimini kullanılarak güvenli, en iyi durumda kod oluşturur. Sınıfın bir üyesinin işaretçisini bildirmeden önce sınıfın tanımlanmasını gerektirir. Varsayılan değer **best_case**. |

*En genel gösterim* bağımsız değişkeni, derleyicinin bir çeviri birimindeki bir sınıfın üyesine yönelik herhangi bir işaretçiye başvurmak için güvenli bir şekilde kullanabileceği en küçük işaretçi gösterimini belirtir. Bağımsız değişkeni şu değerlerden biri olabilir:

| Bağımsız Değişken | Açıklamalar |
|--------------|--------------|
| **single_inheritance** | En genel gösterim, bir üye işlevi işaretçisi olan single-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise hataya neden olur. |
| **multiple_inheritance** | En genel gösterim, bir üye işlev işaretçisi olan multiple-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise hataya neden olur. |
| **virtual_inheritance** | En genel devralma, bir üye işlev işaretçisi olan virtual-inheritance'tır. Hiçbir zaman hataya neden olmaz. `#pragma pointers_to_members(full_generality)` kullanıldığında varsayılan bağımsız değişkendir **virtual_inheritance** . |

> [!CAUTION]
> **Pointers_to_members** pragma 'ı yalnızca etkilemek istediğiniz kaynak kodu dosyasına ve yalnızca herhangi bir `#include` yönergelerinden yerleştirmeniz önerilir. Bu yöntem, pragma 'ın diğer dosyaları etkilemesini ve yanlışlıkla aynı değişken, işlev veya sınıf adı için birden çok tanım belirteceğine ilişkin riski azaltır.

## <a name="example"></a>Örnek

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
