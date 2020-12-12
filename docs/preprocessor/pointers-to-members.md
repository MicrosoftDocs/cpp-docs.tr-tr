---
description: 'Daha fazla bilgi edinin: pointers_to_members pragma'
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
ms.openlocfilehash: 5e1b66ce39f49889a1225facd4bf358231863063
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325725"
---
# <a name="pointers_to_members-pragma"></a>pointers_to_members pragması

**C++ özel**

Sınıf üyesine yönelik işaretçinin, ilişkili sınıf tanımından önce bildirilip belirtimeyeceğini belirtir. İşaretçi boyutunu ve işaretçiyi yorumlamak için gerekli kodu denetlemek için kullanılır.

## <a name="syntax"></a>Syntax

> **#pragma pointers_to_members (** *işaretçi bildirimi* [ **,** *en-genel-temsili* ])

## <a name="remarks"></a>Açıklamalar

[/VMB veya/VMG](../build/reference/vmb-vmg-representation-method.md) derleyici seçeneklerini veya [Devralma anahtar sözcüklerini](../cpp/inheritance-keywords.md)kullanarak kaynak dosyanıza bir **pointers_to_members** pragma yerleştirebilirsiniz.

*İşaretçi bildirimi* bağımsız değişkeni, ilişkili işlev tanımından önce veya sonra bir üyeye işaretçi mi bildirmeyeceğinizi belirtir. *İşaretçi bildirimi* bağımsız değişkeni aşağıdaki iki simgeden biridir:

| Bağımsız Değişken | Yorumlar |
|--------------|--------------|
| **full_generality** | Güvenli, bazen uygun durumda olmayan kod üretir. Üyenin herhangi bir işaretçisi ilişkili sınıf tanımından önce bildirilirse **full_generality** kullanırsınız. Bu bağımsız değişken her zaman *en genel gösterim* bağımsız değişkeni tarafından belirtilen işaretçi gösterimini kullanır. /vmg ile eşdeğerdir. |
| **best_case** | Tüm üye işaretçileri için best-case gösterimini kullanılarak güvenli, en iyi durumda kod oluşturur. Sınıfın bir üyesinin işaretçisini bildirmeden önce sınıfın tanımlanmasını gerektirir. Varsayılan değer **best_case**. |

*En genel gösterim* bağımsız değişkeni, derleyicinin bir çeviri birimindeki bir sınıfın üyesine yönelik herhangi bir işaretçiye başvurmak için güvenli bir şekilde kullanabileceği en küçük işaretçi gösterimini belirtir. Bağımsız değişkeni şu değerlerden biri olabilir:

| Bağımsız Değişken | Yorumlar |
|--------------|--------------|
| **single_inheritance** | En genel gösterim, bir üye işlevi işaretçisi olan single-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise hataya neden olur. |
| **multiple_inheritance** | En genel gösterim, bir üye işlev işaretçisi olan multiple-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise hataya neden olur. |
| **virtual_inheritance** | En genel devralma, bir üye işlev işaretçisi olan virtual-inheritance'tır. Hiçbir zaman hataya neden olmaz. **virtual_inheritance** , kullanıldığında varsayılan bağımsız değişkendir `#pragma pointers_to_members(full_generality)` . |

> [!CAUTION]
> **Pointers_to_members** pragma 'ı yalnızca etkilemek istediğiniz kaynak kodu dosyasına ve yalnızca tüm yönergelerden sonra yerleştirmeniz önerilir `#include` . Bu yöntem, pragma 'ın diğer dosyaları etkilemesini ve yanlışlıkla aynı değişken, işlev veya sınıf adı için birden çok tanım belirteceğine ilişkin riski azaltır.

## <a name="example"></a>Örnek

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
