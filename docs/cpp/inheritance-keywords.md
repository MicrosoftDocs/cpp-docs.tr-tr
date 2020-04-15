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
ms.openlocfilehash: f0aae655540b4d3f9130d9840d77e0abcf270cc2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374095"
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
Bildirilen sınıfın adı.

C++ sınıfın tanımından önce bir sınıf üyesine işaretçi bildirmenizi sağlar. Örneğin:

```cpp
class S;
int S::*p;
```

Yukarıdaki kodda, `p` S sınıfının tamsayı üyesiiçin işaretçi olarak beyan edilir. Ancak, `class S` bu kodda henüz tanımlanmamıştır; sadece ilan edilmiştir. Derleyici böyle bir işaretçiyle karşılaştığında, işaretçinin genelleştirilmiş bir temsilini yapması gerekir. Gösterimin boyutu belirtilen devralma modeline bağlıdır. Derleyiciye bir devralma modeli belirtmenin dört yolu vardır:

- **Üyeye Pointer gösterimi** altındaki IDE'de

- [/vmg](../build/reference/vmb-vmg-representation-method.md) anahtarını kullanarak komut satırında

- [pointers_to_members](../preprocessor/pointers-to-members.md) pragma kullanma

- Kalıtım anahtar kelimelerini **__single_inheritance,** **__multiple_inheritance**ve **__virtual_inheritance**kullanarak. Bu teknik, sınıf başına olarak kalıtım modelini denetler.

    > [!NOTE]
    >  Sınıfı tanımladıktan sonra her zaman bir sınıfın bir üyesine işaretçi bildirirseniz, bu seçeneklerden hiçbirini kullanmanız gerekmez.

Sınıf tanımından önce bir sınıfın bir üyesine işaretçi bildirmek, ortaya çıkan yürütülebilir dosyanın boyutunu ve hızını etkiler. Bir sınıf tarafından kullanılan kalıtım ne kadar karmaşıksa, sınıfın bir üyesini işaretçiyi temsil etmek için gereken bayt sayısı da o kadar büyük türde ve işaretçiyi yorumlamak için gereken kod da o kadar büyüktür. Tek devralma en az karmaşıktır ve sanal devralma en karmaşıktır.

Yukarıdaki örnek aşağıdaki şekilde değiştirilirse:

```cpp
class __single_inheritance S;
int S::*p;
```

komut satırı seçenekleri veya pragmalar ne olursa olsun, üyelerine işaretçiler mümkün olan en küçük gösterimi `class S` kullanır.

> [!NOTE]
> Bir sınıf işaretçisi-üye gösterimaynı ileri bildirimi, o sınıfın üyelerine işaretçileri bildiren her çeviri biriminde ve bildirimler üyelere işaretçiler beyan edilmeden önce bildirge nin gerçekleşmesi gerekir.

Önceki sürümlerle uyumluluk **için, _single_inheritance,** **_multiple_inheritance**ve **_virtual_inheritance** **__single_inheritance**, **__multiple_inheritance**ve **__virtual_inheritance** eşanlamlıdır, derleyici seçeneği [/Za \(Dil uzantılarını devre dışı kılamaz)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
