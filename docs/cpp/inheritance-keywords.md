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
ms.openlocfilehash: 781673582cb2c3086677b05abc6a7eb73eeabdb4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178207"
---
# <a name="inheritance-keywords"></a>Devralınan Anahtar Sözcükler

**Microsoft 'a özgü**

```
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;
```

burada:

*sınıf adı*<br/>
Bildirildiği sınıfın adı.

C++sınıfın tanımından önce bir sınıf üyesine yönelik bir işaretçi bildirmenize olanak tanır. Örneğin:

```cpp
class S;
int S::*p;
```

Yukarıdaki kodda `p`, sınıfının tamsayı üyesine yönelik bir işaretçi olarak bildirilmiştir. Ancak, `class S` henüz bu kodda tanımlı değil; yalnızca bildirilmiştir. Derleyici böyle bir işaretçi ile karşılaştığında, işaretçinin genelleştirilmiş bir gösterimini yapması gerekir. Gösteriminin boyutu belirtilen devralma modeline bağlıdır. Derleyiciye devralma modeli belirtmek için dört yol vardır:

- IDE 'de **üye işaretçisi gösterimi** altında

- [/VMG](../build/reference/vmb-vmg-representation-method.md) anahtarını kullanarak komut satırında

- [Pointers_to_members](../preprocessor/pointers-to-members.md) pragma 'ı kullanma

- Devralma anahtar sözcüklerini **__single_inheritance**, **__multiple_inheritance**ve **__virtual_inheritance**kullanma. Bu teknik, devralma modelini sınıf başına temelinde denetler.

    > [!NOTE]
    >  Sınıfı tanımladıktan sonra sınıfın üyesine her zaman bir işaretçi bildirirseniz, bu seçeneklerden herhangi birini kullanmanız gerekmez.

Sınıf tanımından önce bir sınıfın üyesine yönelik bir işaretçi bildirmek, elde edilen yürütülebilir dosyanın boyutunu ve hızını etkiler. Bir sınıf tarafından kullanılan devralma ne kadar karmaşık olursa, sınıfın bir üyesine yönelik bir işaretçiyi temsil etmek için gereken bayt sayısı ve işaretçiyi yorumlamak için gereken kod daha büyük olur. Tek devralma en az karmaşıktır ve sanal devralma en karmaşıktır.

Yukarıdaki örnek olarak değiştirilirse:

```cpp
class __single_inheritance S;
int S::*p;
```

komut satırı seçenekleri veya pragmalar ne olursa olsun, `class S` üyelerine yönelik işaretçiler olası en küçük gösterimi kullanır.

> [!NOTE]
>  Bir sınıf işaretçisinin üye gösteriminin aynı iletme bildirimi, bu sınıfın üyelerine işaretçiler bildiren her bir çeviri biriminde gerçekleşmelidir ve bu bildirimin, üyelerin işaretçilerine bildirilmeden önce gerçekleşmesi gerekir.

Önceki sürümlerle uyumluluk için **_single_inheritance**, **_multiple_inheritance**ve **_virtual_inheritance** **__single_inheritance**, **__multiple_inheritance**ve **__Virtual_inheritance** Için eş anlamlılardır. [/za \(dil uzantılarını devre dışı bırakma](../build/reference/za-ze-disable-language-extensions.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
