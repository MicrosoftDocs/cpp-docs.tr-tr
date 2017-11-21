---
title: "HStringReference::HStringReference Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs: C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b73e25977b91940031316f6d85c0bcfded4ab3ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference Oluşturucusu
HStringReference sınıfı yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `sizeDest`  
 Şablon parametresi hedef HStringReference arabellek boyutunu belirtir.  
  
 `str`  
 Bir joker karakter dizesi referansı.  
  
 `len`  
 En büyük uzunluğu `str` bu işlemde kullanılacak parametre arabelleği. Varsa `len` değil parametresi belirtilmezse, tüm `str` parametresi kullanılır. Varsa `len` değerinden daha büyük `sizeDest`, `len` ayarlanır `sizeDest`-1.  
  
 `other`  
 Başka bir HStringReference nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu aynı parametre olarak boyut yeni bir HStringReference nesnesini başlatır `str`.  
  
 İkinci oluşturucu başlatır yeni HStringReference nesne boyutu specifeid parametresi tarafından `len`.  
  
 Üçüncü Oluşturucu değerini yeni HStringReference nesnesine başlatır `other` parametresi ve ardından bozar `other` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference sınıfı](../windows/hstringreference-class.md)