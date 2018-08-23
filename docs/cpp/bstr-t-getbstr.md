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
ms.openlocfilehash: 56297f53aa40741a506ea65761d151dcab98c421
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465607"
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
 **GetBSTR** tüm etkiler `_bstr_t` nesneleri paylaşan bir `BSTR`. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve **işleç =**.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için **GetBSTR**.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)