---
description: 'Daha fazla bilgi edinin: üye erişimi'
title: Üye Erişimi
ms.date: 11/04/2016
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
ms.openlocfilehash: c35eb2e7e24da9f8e8988b47ebfd8a59df815cee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161721"
---
# <a name="member-access"></a>Üye Erişimi

Sınıf üyesi erişimi, üye erişim işleci () aşırı yüklendikten sonra denetlenebilir **->** . Bu işleç bu kullanımda birli işleç olarak kabul edilir ve aşırı yüklenmiş işleç işlevi bir sınıf üyesi işlevi olmalıdır. Bu nedenle, bu tür bir işlevin bildirimi şöyledir:

## <a name="syntax"></a>Syntax

```
class-type *operator->()
```

## <a name="remarks"></a>Açıklamalar

Burada *Class-Type* , bu işlecin ait olduğu sınıfın adıdır. Üye erişim işleci işlevi, statik olmayan bir üye işlevi olmalıdır.

Bu işleç (çoğunlukla işaretçi başvuru kaldırma işleci ile birlikte) başvuru kaldırma veya sayım kullanımından önce işaretçileri doğrulayan "akıllı işaretçileri" uygulamak için kullanılır.

Dosyanın başındaki **.** üye erişim işleci aşırı yüklenemez.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](../cpp/operator-overloading.md)
