---
description: 'Daha fazla bilgi edinin: tür Iletme (C++/CLı)'
title: Tür İletme (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
ms.openlocfilehash: 360ca624103c8021c17300f897b1091c13e898a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172888"
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

*Yeni*<br/>
Tür tanımını taşıdığınız derleme.

*türüyle*<br/>
Tanımını başka bir derlemeye taşıdığınız tür.

### <a name="remarks"></a>Açıklamalar

Bir bileşen (derleme) gönderdikten ve istemci uygulamaları tarafından kullanıldıktan sonra, bir türü bileşenden (bütünleştirilmiş kod) başka bir derlemeye taşımak, güncelleştirilmiş bileşeni (ve gerekli diğer derlemeleri) göndermek ve istemci uygulamaları yeniden derlenmeden çalışmaya devam edecektir.

Tür iletme yalnızca mevcut uygulamalar tarafından başvurulan bileşenler için geçerlidir. Bir uygulamayı yeniden yapılandırdığınızda, uygulamada kullanılan herhangi bir tür için uygun derleme başvuruları olmalıdır.

Bir derlemeden bir tür (tür A) iletirken, `TypeForwardedTo` Bu tür için özniteliği ve bir derleme başvurusu eklemeniz gerekir. Başvurduğunuz derleme aşağıdakilerden birini içermelidir:

- A türü için tanım.

- `TypeForwardedTo`A türü için bir öznitelik ve bir derleme başvurusu.

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

Bu nedenle, derleme A.dll oluşturmak için kullanılan bir kaynak kodu dosyası bir tür tanımı ( `ref class MyClass` ) içeriyorsa ve bu tür tanımını derleme B.dll taşımak istiyordunuz:

1. `MyClass`Tür tanımını B.dll oluşturmak için kullanılan bir kaynak kod dosyasına taşıyın.

2. Derleme derlemesi B.dll

3. `MyClass`A.dll oluşturmak için kullanılan kaynak kodundan tür tanımını silin ve aşağıdaki kodla değiştirin:

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Derleme derlemesi A.dll.

5. İstemci uygulamalarını yeniden derlemeden A.dll kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`
