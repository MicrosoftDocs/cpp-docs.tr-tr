---
title: _com_ptr_t ilişkisel işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::operator>
- _com_ptr_t::operator>=
- _com_ptr_t::operator<=
- _com_ptr_t::operator==
- _com_ptr_t::operator!=
- _com_ptr_t::operator<
dev_langs:
- C++
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- '!= operator'
- operator > [C++], pointers
- operator>= [C++], pointers
- operator < [C++], pointers
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- operator== [C++], pointers
- operator == [C++], pointers
- <= operator [C++], with specific objects
- relational operators [C++], _com_ptr_t class
- operator >= [C++], pointers
- operator != [C++], relational operators
- operator <= [C++], pointers
- '> operator [C++], comparing specific objects'
- operator<= [C++], pointers
- operator< [C++], pointers
- == operator [C++], with specific Visual C++ objects
ms.assetid: 5ae4028c-33ee-485d-bbda-88d2604d6d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4502f4752d094805ac9e31bbd4fdcbd1b0fdbdab
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403267"
---
# <a name="comptrt-relational-operators"></a>_com_ptr_t İlişkisel İşleçleri
**Microsoft'a özgü**  
  
 NULL veya başka bir akıllı işaretçinin, ham arabirim işaretçisi için akıllı işaretçi nesnesinin karşılaştırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename _OtherIID>   
bool operator==( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>    
bool operator==( _com_ptr_t<_OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator==( _InterfaceType* p );  
  
template<>   
bool operator==( Interface* p );  
  
template<>   
bool operator==( const _com_ptr_t& p ) throw();  
  
template<>   
bool operator==( _com_ptr_t& p ) throw();  
  
bool operator==( Int null );  
  
template<typename _OtherIID>   
bool operator!=( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>   
bool operator!=( _com_ptr_t<_OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator!=( _InterfaceType* p );  
  
bool operator!=( Int null );  

template<typename _OtherIID>   
bool operator<( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>   
bool operator<( _com_ptr_t<_OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator<( _InterfaceType* p );  

template<typename _OtherIID>   
bool operator>( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>   
bool operator>(_com_ptr_t< _OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator>( _InterfaceType* p );  
  
template<typename _OtherIID>   
bool operator<=( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>   
bool operator<=( _com_ptr_t<_OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator<=( _InterfaceType* p );  
  
template<typename _OtherIID>  
bool operator>=( const _com_ptr_t<_OtherIID>& p );  
  
template<typename _OtherIID>   
bool operator>=( _com_ptr_t<_OtherIID>& p );  
  
template<typename _InterfaceType>   
bool operator>=( _InterfaceType* p );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir akıllı işaretçi nesnesinin diğerine karşılaştırır, akıllı işaretçinin, ham arabirim işaretçisi veya NULL. NULL işaretçi testleri dışında bu işleçlerden önce her iki işaretçiler için sorgu `IUnknown`ve sonuçlarını karşılaştırın.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)