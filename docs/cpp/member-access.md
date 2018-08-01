---
title: Üye erişimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99f65d2b03f54eb16db56bf81948aadfb184cfa1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402373"
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