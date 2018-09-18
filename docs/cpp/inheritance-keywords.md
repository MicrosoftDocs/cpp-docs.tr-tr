---
title: Devralma anahtar sözcükleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1106ad878f4053cacae67d9d0e343e9469b1a1c1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061181"
---
# <a name="inheritance-keywords"></a>Devralınan Anahtar Sözcükler

**Microsoft'a özgü**

```
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;
```

burada:

*sınıf adı*<br/>
Bildirilen sınıf adı.

C++ sınıfının tanımını önce bir sınıf üyesine bir işaretçi bildirmek sağlar. Örneğin:

```cpp
class S;
int S::*p;
```

Yukarıdaki kodda `p` S. sınıfın tamsayı üyesine bir işaretçi olarak bildirilmiştir Ancak, `class S` vardır; bu kodu, tanımlanmış değil ancak yalnızca bildirilmiş. Derleyici bu tür bir işaretçi karşılaştığında, genelleştirilmiş bir işaretçi gösterimini yapmanız gerekir. Belirtilen devralma modeline gösterimi boyutuna bağlıdır. Derleyici bir devralma modeline belirtmek için dört yolu vardır:

- IDE'de altında **işaretçi-üye gösterimi**

- Komut satırı kullanarak [/vmg](../build/reference/vmb-vmg-representation-method.md) geçiş

- Kullanarak [pointers_to_members](../preprocessor/pointers-to-members.md) pragması

- Devralma anahtar sözcükleri kullanarak **__single_inheritance**, **__multiple_inheritance**, ve **__virtual_inheritance**. Bu teknik, her sınıf devralma modeli denetler.

    > [!NOTE]
    >  Her zaman bir işaretçiyi bir sınıf üyesi için sınıf tanımlandıktan sonra bildirirseniz, bu seçeneklerden birini kullanmanız gerekmez.

Sınıf tanımı önce bir sınıf üyesinin işaretçisi bildirme, boyutu ve elde edilen çalıştırılabilir dosyayı hızını etkiler. Devralma bir sınıfla büyük bir işaretçi sınıf ve daha büyük bir üye için işaretçiyi yorumlamak için gerekli kodu temsil etmek için gereken bayt sayısını kullanılan daha karmaşık. Tek devralma az karmaşıktır ve en karmaşık olan sanal inheritance'tır.

Yukarıdaki örnekte değiştirilirse:

```cpp
class __single_inheritance S;
int S::*p;
```

komut satırı seçenekleri veya pragmalar, işaretçileri bağımsız olarak `class S` en küçük olası gösterimi kullanır.

> [!NOTE]
>  Aynı İleri dönük bildirimi bir sınıf üye işaretçisi gösteriminin söz konusu sınıfın üyeleri için işaretçiler bildirir her çeviri birimi içinde gerçekleşmesi gerektiğini ve üye işaretçileri ifade önce bildirimi olmamalıdır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)