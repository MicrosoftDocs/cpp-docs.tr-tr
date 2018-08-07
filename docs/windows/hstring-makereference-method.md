---
title: HString::MakeReference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 673d5b10706580303f179ee453495b581d96eda3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608341"
---
# <a name="hstringmakereference-method"></a>HString::MakeReference Yöntemi
Oluşturur bir `HStringReference` nesnesinden belirtilen dize parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
### <a name="parameters"></a>Parametreler  
 *sizeDest*  
 Hedef boyutunu belirten bir şablon parametresi `HStringReference` arabellek.  
  
 *str*  
 Bir geniş karakter dizesi bir başvuru.  
  
 *Len*  
 En büyük uzunluğunu *str* parametre arabelleği bu işlemi kullanmak için. Varsa *len* parametresi belirtilmediyse, tüm *str* parametresi kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HStringReference` değeri belirtilen türle aynı olan nesne *str* parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)