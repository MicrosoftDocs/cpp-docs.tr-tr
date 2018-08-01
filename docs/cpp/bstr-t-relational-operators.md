---
title: _bstr_t ilişkisel işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
dev_langs:
- C++
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- operator<= [C++], bstr
- '!= operator'
- operator == [C++], bstr
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- relational operators [C++], _bstr_t class
- operator== [C++], bstr
- <= operator [C++], with specific objects
- operator <= [C++], bstr
- operator >= [C++], bstr
- operator != [C++], relational operators
- '> operator [C++], comparing specific objects'
- operator< [C++], bstr
- == operator [C++], with specific Visual C++ objects
- operator>= [C++], bstr
- operator < [C++], bstr
- operator > [C++], bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97595b29c2d79cd6209479e39987208cafe6f0f8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401788"
---
# <a name="bstrt-relational-operators"></a>_bstr_t İlişkisel İşleçleri
**Microsoft'a özgü**  
  
 İki karşılaştırır `_bstr_t` nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool operator!( ) const throw( );   
bool operator==(const _bstr_t& str) const throw( );  
bool operator!=(const _bstr_t& str) const throw( );  
bool operator<(const _bstr_t& str) const throw( );  
bool operator>(const _bstr_t& str) const throw( );  
bool operator<=(const _bstr_t& str) const throw( );  
bool operator>=(const _bstr_t& str) const throw( );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleçler karşılaştırabilirsiniz `_bstr_t` sözlüksel nesnelerini. İşleçler TRUE döndürür. karşılaştırmayı tutarsanız, aksi takdirde false değerini döndürür.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)