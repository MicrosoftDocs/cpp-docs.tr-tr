---
title: Açık örnek oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85ea920dc01f408c7723fb082e6a0e60fa9a00e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110672"
---
# <a name="explicit-instantiation"></a>Açık Örnekleme

Gerçekte kodunuzda kullanmadan bir şablonlu sınıfın veya işlevin örneklemesini oluşturmak için açık örneklemeyi kullanabilirsiniz. Bu, dağıtım için şablonlar kullanın kitaplık (.lib) dosyaları oluştururken yararlı olduğundan, örneklenmemiş şablon tanımları nesne (.obj) dosyalarına konmaz.

Bu kod örneğini açıkça oluşturur `MyStack` için **int** değişkenleri ve altı öğe:

```cpp
template class MyStack<int, 6>;
```

Bu deyim, bir nesne için herhangi bir depolama alanı ayırmadan bir `MyStack` örneklemesi oluşturur. Tüm üyeler için kod oluşturulur.

Bir sonraki satır yalnızca oluşturucu üye işlevinin örneğini açıkça oluşturur:

```cpp
template MyStack<int, 6>::MyStack( void );
```

İşlev şablonları belirli tür bağımsız değişkeni, yeniden bildirmek için örnekte gösterildiği gibi kullanarak açıkça oluşturabileceğiniz [işlev şablonu örneklemesi](../cpp/function-template-instantiation.md).

Kullanabileceğiniz **extern** üyeleri örneklemelerinin otomatik olarak oluşturulmasını önlemek için anahtar sözcüğü. Örneğin:

```cpp
extern template class MyStack<int, 6>;
```

Benzer şekilde, belirli üyeleri dış ve örneklenmemiş olarak işaretleyebilirsiniz:

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

Kullanabileceğiniz **extern** birden fazla nesne modülünde aynı örnekleme kodunu oluşturmasını derleyici tutmak anahtar sözcüğü. İşlev çağrılırsa, belirtilen açık şablon parametrelerini en az bir bağlantılı modülde kullanarak şablon işlevinin örneğini oluşturmalısınız, aksi takdirde program oluşturulduğunda bir bağlayıcı hatası alırsınız.

> [!NOTE]
>  **Extern** uzmanlıktaki anahtar sözcüğü yalnızca geçerli sınıf gövdesinin dışında tanımlanmış üye işlevleri için. Sınıf bildirimi içinde tanımlanmış işlevler, satır içi işlevleri olarak kabul edilir ve her zaman örneği oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Şablonları](../cpp/function-templates.md)