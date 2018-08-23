---
title: Tür iletme (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, Visual C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44b76e1a3eaff778fc64806eec49eff1bf2a10eb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596675"
---
# <a name="type-forwarding-ccli"></a>Tür İletme (C++/CLI)

*Tür iletme* şekilde derleme A'ya kullanan istemcileri yeniden derlemenize gerek yoktur, bir tür başka bir derlemeye (derleme B), bir derlemeye (a derlemesi) taşımanızı sağlar

## <a name="all-platforms"></a>Tüm Platformlar

Bu özellik tüm çalışma zamanları desteklenmiyor.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Bu özellik, Windows çalışma zamanı'nda desteklenmiyor.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki kod örneği, tür iletme kullanma işlemini gösterir.

### <a name="syntax"></a>Sözdizimi

```
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>Parametreler

*new*  
Tür tanımını taşıdığınız derleme.

*Türü*  
Türü tanımı başka bir derlemeye taşıyor.

### <a name="remarks"></a>Açıklamalar

Bir bileşen (derleme) gelir ve sonra istemci uygulamalar tarafından kullanılan, tür iletme türü başka bir derlemeye (derleme) bileşeninden taşımak, güncelleştirilen bileşenin (ve gereken ek bütünleştirilmiş kodları) gönderin ve istemci kullanabilirsiniz uygulamaları yeniden derlenen olmadan çalışmaya devam eder.

Tür iletme yalnızca var olan uygulamalar tarafından başvurulan bileşen için çalışır. Bir uygulamayı yeniden derlediğinizde, uygulamada kullanılan türler için uygun derleme başvurularını olmalıdır.

Bir derlemeden bir tür (tür A) iletirken eklemelisiniz `TypeForwardedTo` bir bütünleştirilmiş kod başvurusu yanı sıra, bu tür için özniteliği. Başvuru bütünleştirilmiş kod, aşağıdakilerden birini içermelidir:

- Tür a tanımı

- A `TypeForwardedTo` özniteliği için bir bütünleştirilmiş kod başvurusu yanı sıra yazın.

İletilebilir türleri şunlardır:

- başvuru sınıfları

- değer sınıfları

- numaralandırmalar

- arabirimler

Aşağıdaki türleri iletilemiyor:

- Genel türler

- Yerel türler

- İç içe türleri (iç içe geçmiş bir tür iletmek istiyorsanız, kapsayan tür iletme)

Bir tür, ortak dil çalışma zamanını hedefleyen herhangi bir dilde yazılmış bir derlemeye iletebilirsiniz.

Bunu, bir tür tanımı A.dll derlemesi oluşturmak için kullanılan bir kaynak kodu dosyası içeriyorsa (`ref class MyClass`), ve bu tür taşımak istiyordu B.dll derleme tanımına yaptığınız:

1. Taşıma `MyClass` B.dll oluşturmak için kullanılan bir kaynak kodu dosyası için tanım yazın.

2. B.dll derleme

3. Silme `MyClass` tanımından A.dll oluşturup aşağıdakiyle değiştirin kullanılan kaynak kodu yazın:

    ```
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Bütünleştirilmiş kod A.dll oluşturun.

5. İstemci uygulamalarını yeniden derlemeye gerek kalmadan A.dll kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`