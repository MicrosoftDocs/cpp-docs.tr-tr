---
title: Devralınan Anahtar Sözcükler
ms.date: 11/04/2016
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
ms.openlocfilehash: bc9afdcb7971c478c1cad9185cece57ea6326a48
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233736"
---
# <a name="inheritance-keywords"></a>Devralınan Anahtar Sözcükler

**Microsoft'a Özgü**

```
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;
```

burada:

*sınıf adı*<br/>
Bildirildiği sınıfın adı.

C++, sınıfın tanımından önce bir sınıf üyesine yönelik bir işaretçi bildirmenize olanak tanır. Örnek:

```cpp
class S;
int S::*p;
```

Yukarıdaki kodda, `p` sınıfının tamsayı üyesine yönelik bir işaretçi olarak bildirilmiştir. Ancak, `class S` Bu kodda henüz tanımlanmamış; yalnızca bildirilmiştir. Derleyici böyle bir işaretçi ile karşılaştığında, işaretçinin genelleştirilmiş bir gösterimini yapması gerekir. Gösteriminin boyutu belirtilen devralma modeline bağlıdır. Derleyiciye devralma modeli belirtmek için dört yol vardır:

- IDE 'de **üye işaretçisi gösterimi** altında

- [/VMG](../build/reference/vmb-vmg-representation-method.md) anahtarını kullanarak komut satırında

- [Pointers_to_members](../preprocessor/pointers-to-members.md) pragma 'ı kullanma

- Devralma anahtar sözcüklerini kullanarak **`__single_inheritance`** , **`__multiple_inheritance`** ve **`__virtual_inheritance`** . Bu teknik, devralma modelini sınıf başına temelinde denetler.

    > [!NOTE]
    >  Sınıfı tanımladıktan sonra sınıfın üyesine her zaman bir işaretçi bildirirseniz, bu seçeneklerden herhangi birini kullanmanız gerekmez.

Sınıf tanımından önce bir sınıfın üyesine yönelik bir işaretçi bildirmek, elde edilen yürütülebilir dosyanın boyutunu ve hızını etkiler. Bir sınıf tarafından kullanılan devralma ne kadar karmaşık olursa, sınıfın bir üyesine yönelik bir işaretçiyi temsil etmek için gereken bayt sayısı ve işaretçiyi yorumlamak için gereken kod daha büyük olur. Tek devralma en az karmaşıktır ve sanal devralma en karmaşıktır.

Yukarıdaki örnek olarak değiştirilirse:

```cpp
class __single_inheritance S;
int S::*p;
```

komut satırı seçenekleri veya pragmalar ne olursa olsun, üye işaretçileri `class S` olası en küçük gösterimi kullanır.

> [!NOTE]
> Bir sınıf işaretçisinin üye gösteriminin aynı iletme bildirimi, bu sınıfın üyelerine işaretçiler bildiren her bir çeviri biriminde gerçekleşmelidir ve bu bildirimin, üyelerin işaretçilerine bildirilmeden önce gerçekleşmesi gerekir.

Önceki sürümlerle uyumluluk için, **_single_inheritance**, **_multiple_inheritance**ve **_virtual_inheritance** **`__single_inheritance`** ,, **`__multiple_inheritance`** ve **`__virtual_inheritance`** [< za \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, ve için eş anlamlılardır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
