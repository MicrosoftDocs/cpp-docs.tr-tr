---
title: _bstr_t::GetBSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3041e8a4ece0ddff813b7ef9cd2ccb258e520a82
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940488"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft'a özgü**  
  
 Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başlangıcı `BSTR` tarafından Sarmalanan `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetBSTR`, `_bstr_t` paylaşan tüm `BSTR` nesnelerini etkiler. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve ve **işleç =**.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için `GetBSTR`.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)