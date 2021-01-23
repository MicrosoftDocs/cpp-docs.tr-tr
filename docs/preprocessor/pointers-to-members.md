---
description: pragmaMicrosoft C/C++ ' da pointers_to_members yönergesi hakkında daha fazla bilgi edinin
title: pointers_to_members pragma
ms.date: 01/22/2021
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragma, pointers_to_members
- members, pointers to
- pointers_to_members pragma
no-loc:
- pragma
ms.openlocfilehash: 7f2ca20b70d477e66a38d2a57e489d64c4179191
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713382"
---
# <a name="pointers_to_members-no-locpragma"></a>`pointers_to_members` pragma

**C++ özel**

Sınıf üyesine yönelik işaretçinin, ilişkili sınıf tanımından önce bildirilip belirtimeyeceğini belirtir. İşaretçi boyutunu ve işaretçiyi yorumlamak için gerekli kodu denetlemek için kullanılır.

## <a name="syntax"></a>Syntax

> **`#pragma pointers_to_members(`***işaretçi bildirimi* [ **`,`** *en-genel-temsili* ]**`)`**

## <a name="remarks"></a>Açıklamalar

**`pointers_to_members`** pragma [ `/vmb` Ya `/vmg`](../build/reference/vmb-vmg-representation-method.md) da derleyici seçeneklerini veya [Devralma anahtar sözcüklerini](../cpp/inheritance-keywords.md)kullanarak kaynak dosyanıza bir alternatif olarak yerleştirebilirsiniz.

*İşaretçi bildirimi* bağımsız değişkeni, ilişkili işlev tanımından önce veya sonra bir üyeye işaretçi mi bildirmeyeceğinizi belirtir. *İşaretçi bildirimi* bağımsız değişkeni aşağıdaki iki simgeden biridir:

| Bağımsız Değişken | Yorumlar |
|--------------|--------------|
| **`full_generality`** | Güvenli, bazen uygun durumda olmayan kod üretir. **`full_generality`** Bir üyeye yönelik herhangi bir işaretçi ilişkili sınıf tanımından önce bildirilirse kullanırsınız. Bu bağımsız değişken her zaman *en genel gösterim* bağımsız değişkeni tarafından belirtilen işaretçi gösterimini kullanır. İle eşdeğerdir **`/vmg`** . |
| **`best_case`** | Tüm üye işaretçileri için best-case gösterimini kullanılarak güvenli, en iyi durumda kod oluşturur. Sınıfın bir üyesinin işaretçisini bildirmeden önce sınıfın tanımlanmasını gerektirir. Varsayılan değer **`best_case`** . |

*En genel gösterim* bağımsız değişkeni, derleyicinin bir çeviri birimindeki bir sınıfın üyesine yönelik herhangi bir işaretçiye başvurmak için güvenli bir şekilde kullanabileceği en küçük işaretçi gösterimini belirtir. Bağımsız değişkeni şu değerlerden biri olabilir:

| Bağımsız Değişken | Yorumlar |
|--------------|--------------|
| **`single_inheritance`** | En genel gösterim, bir üye işlevi işaretçisi olan single-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise hataya neden olur. |
| **`multiple_inheritance`** | En genel gösterim, bir üye işlev işaretçisi olan multiple-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise hataya neden olur. |
| **`virtual_inheritance`** | En genel devralma, bir üye işlev işaretçisi olan virtual-inheritance'tır. Hiçbir zaman hataya neden olmaz. **`virtual_inheritance`** , kullanıldığında varsayılan bağımsız değişkendir `#pragma pointers_to_members(full_generality)` . |

> [!CAUTION]
> **`pointers_to_members`** pragma Yalnızca, etkilemek istediğiniz kaynak kodu dosyasına ve yalnızca herhangi bir yönergelerden sonra ' yi yerleştirmeniz önerilir `#include` . Bu yöntem, pragma diğer dosyaları etkileyecek riski azaltır ve yanlışlıkla aynı değişken, işlev veya sınıf adı için birden çok tanım belirtmenizi ister.

## <a name="example"></a>Örnek

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
