---
title: Tür İletme (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
ms.openlocfilehash: 0803ecc2ffb2da2748b1ef063481aa2571f27f50
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171937"
---
# <a name="type-forwarding-ccli"></a>Tür İletme (C++/CLI)

*Tür iletme* bir türü bir derlemeden (derleme a) başka bir derlemeye (derleme B) taşımanızı sağlar. bu şekilde, derleme a kullanan istemcileri yeniden derlemek gerekli değildir.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Bu özellik Windows Çalışma Zamanı desteklenmez.

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki kod örneği, tür iletmenin nasıl kullanılacağını göstermektedir.

### <a name="syntax"></a>Sözdizimi

```cpp
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>Parametreler

*new*<br/>
Tür tanımını taşıdığınız derleme.

*type*<br/>
Tanımını başka bir derlemeye taşıdığınız tür.

### <a name="remarks"></a>Açıklamalar

Bir bileşen (derleme) gönderdikten ve istemci uygulamaları tarafından kullanıldıktan sonra, bir türü bileşenden (bütünleştirilmiş kod) başka bir derlemeye taşımak için tür iletmeyi kullanabilirsiniz, güncelleştirilmiş bileşeni (ve gerekli tüm ek derlemeleri) ve istemcisini gönderebilirsiniz. uygulamalar yeniden derlenmeden çalışmaya devam edecektir.

Tür iletme yalnızca mevcut uygulamalar tarafından başvurulan bileşenler için geçerlidir. Bir uygulamayı yeniden yapılandırdığınızda, uygulamada kullanılan herhangi bir tür için uygun derleme başvuruları olmalıdır.

Bir derlemeden bir tür (tür A) iletirken, bu tür için `TypeForwardedTo` özniteliği ve bir derleme başvurusu eklemeniz gerekir. Başvurduğunuz derleme aşağıdakilerden birini içermelidir:

- A türü için tanım.

- A türü için bir `TypeForwardedTo` özniteliği ve bir derleme başvurusu.

İletilebileceği türlerin örnekleri şunlardır:

- başvuru sınıfları

- değer sınıfları

- numaralandırmalar

- arabirimler

Aşağıdaki türleri iletemezsiniz:

- Genel türler

- Yerel türler

- İç içe türler (iç içe geçmiş bir türü iletmek istiyorsanız kapsayan türü iletmelisiniz)

Bir türü, ortak dil çalışma zamanını hedefleyen herhangi bir dilde yazılmış bir derlemeye iletebilirsiniz.

Bu nedenle, bir. dll derlemesi oluşturmak için kullanılan bir kaynak kodu dosyası bir tür tanımı (`ref class MyClass`) içeriyorsa ve bu tür tanımını derleme B. dll ' ye taşımak istiyordunuz:

1. `MyClass` tür tanımını B. dll derlemek için kullanılan bir kaynak kod dosyasına taşıyın.

2. Derleme derlemesi B. dll

3. Bir. dll dosyası oluşturmak için kullanılan kaynak kodundan `MyClass` tür tanımını silin ve aşağıdaki ile değiştirin:

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Derleme A. dll.

5. İstemci uygulamalarını yeniden derlemeden bir. dll kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`
