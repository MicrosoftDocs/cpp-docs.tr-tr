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
ms.openlocfilehash: 026b036e3a4dad0fb88600cb64ac3da892eba2b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [HString sınıfı](../windows/hstring-class.md)