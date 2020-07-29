---
title: Açık Örnekleme
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
ms.openlocfilehash: 4b1808791110c4eed237d18436897dac59170206
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232306"
---
# <a name="explicit-instantiation"></a>Açık Örnekleme

Gerçekte kodunuzda kullanmadan bir şablonlu sınıfın veya işlevin örneklemesini oluşturmak için açık örneklemeyi kullanabilirsiniz. Bu, dağıtım için şablonlar kullanın kitaplık (.lib) dosyaları oluştururken yararlı olduğundan, örneklenmemiş şablon tanımları nesne (.obj) dosyalarına konmaz.

Bu kod `MyStack` **`int`** , değişkenler ve altı öğe için açık olarak başlatılır:

```cpp
template class MyStack<int, 6>;
```

Bu deyim, bir nesne için herhangi bir depolama alanı ayırmadan bir `MyStack` örneklemesi oluşturur. Tüm üyeler için kod oluşturulur.

Bir sonraki satır yalnızca oluşturucu üye işlevinin örneğini açıkça oluşturur:

```cpp
template MyStack<int, 6>::MyStack( void );
```

İşlev [şablonu örneklemede](../cpp/function-template-instantiation.md)örneğinde gösterildiği gibi, yeniden bildirmek üzere belirli bir tür bağımsız değişkeni kullanarak işlev şablonlarının örneğini açıkça oluşturabilirsiniz.

**`extern`** Üyelerin otomatik olarak örneklenmesini engellemek için anahtar sözcüğünü kullanabilirsiniz. Örnek:

```cpp
extern template class MyStack<int, 6>;
```

Benzer şekilde, belirli üyeleri dış ve örneklenmemiş olarak işaretleyebilirsiniz:

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

**`extern`** Derleyicinin aynı örnek oluşturma kodunu birden fazla nesne modülünde oluşturmasını önlemek için anahtar sözcüğünü kullanabilirsiniz. İşlev çağrılırsa, belirtilen açık şablon parametrelerini en az bir bağlantılı modülde kullanarak şablon işlevinin örneğini oluşturmalısınız, aksi takdirde program oluşturulduğunda bir bağlayıcı hatası alırsınız.

> [!NOTE]
> **`extern`** Özelleşmenin anahtar sözcüğü yalnızca sınıfın gövdesi dışında tanımlanan üye işlevleri için geçerlidir. Sınıf bildirimi içinde tanımlanmış işlevler, satır içi işlevleri olarak kabul edilir ve her zaman örneği oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[İşlev şablonları](../cpp/function-templates.md)
