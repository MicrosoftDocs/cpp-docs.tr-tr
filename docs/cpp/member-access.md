---
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
ms.openlocfilehash: 34527f818b135fd5af629ebb69feaffd03b715fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617304"
---
# <a name="member-access"></a>Üye Erişimi

Sınıf üyesi erişimi, üye erişim işleci aşırı yüklenerek denetlenebilir (**->**). Bu işleç bu kullanımda birli işleç olarak kabul edilir ve aşırı yüklenmiş işleç işlevi bir sınıf üyesi işlevi olmalıdır. Bu nedenle, bu tür bir işlevin bildirimi şöyledir:

## <a name="syntax"></a>Sözdizimi

```
class-type *operator->()
```

## <a name="remarks"></a>Açıklamalar

Burada *sınıf türü* Bu işlecin ait olduğu sınıfın adıdır. Üye erişim işleci işlevi, statik olmayan bir üye işlevi olmalıdır.

Bu işleç (çoğunlukla işaretçi başvuru kaldırma işleci ile birlikte) başvuru kaldırma veya sayım kullanımından önce işaretçileri doğrulayan "akıllı işaretçileri" uygulamak için kullanılır.

**.** üye erişim işleci aşırı yüklenemez.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)