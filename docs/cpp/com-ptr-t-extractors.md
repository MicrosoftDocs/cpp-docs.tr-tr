---
title: "_com_ptr_t ayıklayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs: C++
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73e2dca693939765e700d51b6caab0815c6d5e7e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrt-extractors"></a>_com_ptr_t Ayıklayıcıları
**Microsoft özel**  
  
 Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      operator Interface*( ) const throw( );   
operator Interface&( ) const;   
Interface& operator*( ) const;   
Interface* operator->( ) const;   
Interface** operator&( ) throw( );   
operator bool( ) const throw( );  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
-   **işleç arabirimi\***  olabilir kapsüllenmiş arabirim işaretçisi döndürür **NULL**.  
  
-   **işleç arabirimi &** kapsüllenmiş arabirim işaretçisi bir başvuru döndürür ve işaretçi ise hata sorunlarını **NULL**.  
  
-   **İşleç\***  bir akıllı işaretçi nesne dizinindeymiş gibi başvuru yapıldı zaman gerçek kapsüllenmiş arabirimi üstlenmesini sağlar.  
  
-   **-> işleci** bir akıllı işaretçi nesne dizinindeymiş gibi başvuru yapıldı zaman gerçek kapsüllenmiş arabirimi üstlenmesini sağlar.  
  
-   **operator &** ile değiştirerek tüm kapsüllenmiş arabirimi işaretçisi serbest **NULL**ve kapsüllenmiş işaretçi adresini döndürür. Bu akıllı işaretçiyi olan bir işlev adresiyle geçirilmesini sağlar bir **çıkışı** parametresi üzerinden bir arabirim işaretçisi döndürür.  
  
-   **işleç bool değeri** koşullu ifadesinde kullanılabilmesi için bir akıllı işaretçi nesnesi sağlar. Bu işleç döndürür **true** işaretçinin değilse **NULL**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)