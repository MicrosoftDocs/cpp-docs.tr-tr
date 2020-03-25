---
title: Açık Örnekleme
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
ms.openlocfilehash: dbe8bebf91a174e07c7c5cce8e9caf1cf3432edf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180036"
---
# <a name="explicit-instantiation"></a>Açık Örnekleme

Gerçekte kodunuzda kullanmadan bir şablonlu sınıfın veya işlevin örneklemesini oluşturmak için açık örneklemeyi kullanabilirsiniz. Bu, dağıtım için şablonlar kullanın kitaplık (.lib) dosyaları oluştururken yararlı olduğundan, örneklenmemiş şablon tanımları nesne (.obj) dosyalarına konmaz.

Bu kod, **int** değişkenleri ve altı öğe için `MyStack` açıkça başlatır:

```cpp
template class MyStack<int, 6>;
```

Bu deyim, bir nesne için herhangi bir depolama alanı ayırmadan bir `MyStack` örneklemesi oluşturur. Tüm üyeler için kod oluşturulur.

Bir sonraki satır yalnızca oluşturucu üye işlevinin örneğini açıkça oluşturur:

```cpp
template MyStack<int, 6>::MyStack( void );
```

İşlev [şablonu örneklemede](../cpp/function-template-instantiation.md)örneğinde gösterildiği gibi, yeniden bildirmek üzere belirli bir tür bağımsız değişkeni kullanarak işlev şablonlarının örneğini açıkça oluşturabilirsiniz.

Üyelerin otomatik olarak örneklenmesini engellemek için **extern** anahtar sözcüğünü kullanabilirsiniz. Örneğin:

```cpp
extern template class MyStack<int, 6>;
```

Benzer şekilde, belirli üyeleri dış ve örneklenmemiş olarak işaretleyebilirsiniz:

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

Derleyicinin aynı örnek oluşturma kodunu birden fazla nesne modülünden oluşturmasını sağlamak için **extern** anahtar sözcüğünü kullanabilirsiniz. İşlev çağrılırsa, belirtilen açık şablon parametrelerini en az bir bağlantılı modülde kullanarak şablon işlevinin örneğini oluşturmalısınız, aksi takdirde program oluşturulduğunda bir bağlayıcı hatası alırsınız.

> [!NOTE]
>  Uzmandaki **extern** anahtar sözcüğü yalnızca, sınıfının gövdesi dışında tanımlanan üye işlevleri için geçerlidir. Sınıf bildirimi içinde tanımlanmış işlevler, satır içi işlevleri olarak kabul edilir ve her zaman örneği oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Şablonları](../cpp/function-templates.md)
