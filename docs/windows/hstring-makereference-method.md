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
ms.openlocfilehash: e30b3ea3c6b791eb654a6fbbe91b3c87353f31c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringmakereference-method"></a>HString::MakeReference Yöntemi
HStringReference nesneyi belirtilen string parametresinden oluşturur.  
  
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
  
#### <a name="parameters"></a>Parametreler  
 `sizeDest`  
 Şablon parametresi hedef HStringReference arabellek boyutunu belirtir.  
  
 `str`  
 Bir joker karakter dizesi referansı.  
  
 `len`  
 En büyük uzunluğu `str` bu işlemde kullanılacak parametre arabelleği. Varsa `len` değil parametresi belirtilmezse, tüm `str` parametresi kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değeri belirtilen türle aynı olan bir HStringReference nesne `str` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)