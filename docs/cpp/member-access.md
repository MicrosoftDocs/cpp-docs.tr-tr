---
title: "Üye erişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 03a382191e78780aa350741b9cfceac11305cdcb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="member-access"></a>Üye Erişimi
Üye erişimi işleci aşırı yüklemesi tarafından sınıf üye erişimi denetlenebilir (**->**). Bu işleç bu kullanımda birli işleç olarak kabul edilir ve aşırı yüklenmiş işleç işlevi bir sınıf üyesi işlevi olmalıdır. Bu nedenle, bu tür bir işlevin bildirimi şöyledir:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
class-type *operator->()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada *sınıf türü* bu işleci ait olduğu sınıfın adı. Üye erişim işleci işlevi, statik olmayan bir üye işlevi olmalıdır.  
  
 Bu işleç (çoğunlukla işaretçi başvuru kaldırma işleci ile birlikte) başvuru kaldırma veya sayım kullanımından önce işaretçileri doğrulayan "akıllı işaretçileri" uygulamak için kullanılır.  
  
 **.** üye erişimi işleci aşırı yüklenemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç aşırı yüklemesi](../cpp/operator-overloading.md)