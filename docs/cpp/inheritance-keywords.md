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
ms.openlocfilehash: 656ee7ed38c24c9f3b8881f84d8e33ca81e3d936
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183498"
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

Önceki sürümlerle uyumluluk için **_single_inheritance**, **_multiple_inheritance**, ve **_virtual_inheritance** için eş anlamlı sözcükler olan **__ single_inheritance**, **__multiple_inheritance**, ve **__virtual_inheritance** sürece derleyici seçeneği [/Za \(dil devre dışı bırak Uzantılar)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)