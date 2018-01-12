---
title: "messages_base sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xlocmes/std::messages_base
dev_langs: C++
helpviewer_keywords: messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54efcdb0b537563f46ce56f91ba5bd7805485824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="messagesbase-class"></a>messages_base Sınıfı
Temel sınıf tanımlar bir `int` türü kataloğun iletileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Türü kataloğun türü için eş anlamlı olduğundan `int` iletileri olası dönüş değerleri açıklayan:: [do_open](../standard-library/messages-class.md#do_open).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



