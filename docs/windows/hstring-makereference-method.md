---
title: "HString::MakeReference yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs: C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e2eba5756f2c18830c4c8fe7e16f2751ea61ac1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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