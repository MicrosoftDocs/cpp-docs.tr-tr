---
title: _com_ptr_t ayıklayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1343d7dd5f6a35bb222b731294ec897116b9e4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)