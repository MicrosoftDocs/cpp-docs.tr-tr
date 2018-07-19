---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4895153abe248265e0aacfbe636b9a4bd46ed205
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941203"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft'a özgü**  
  
 Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetAddress`, `_bstr_t` paylaşan tüm `BSTR` nesnelerini etkiler. Birden fazla `_bstr_t` paylaşabileceğiniz bir `BSTR` kopya oluşturucu kullanılarak ve ve **işleç =**.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanarak bir örnek için `GetAddress`.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)