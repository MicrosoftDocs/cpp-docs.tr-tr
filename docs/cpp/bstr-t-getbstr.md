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
ms.openlocfilehash: 8863f3a6c37693ec28f931c2af4cb0d299788daa
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402669"
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
 **GetBSTR** tüm etkiler `_bstr_t` nesneleri paylaşan bir `BSTR`. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve ve **işleç =**.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için **GetBSTR**.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)