---
title: "HString::Set yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs: C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cc761ea9d79fbca358b8aab68944560c58a170ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringset-method"></a>HString::Set Yöntemi
Belirtilen geniş karakter dizesi veya HString parametresi için geçerli HString nesnenin değerini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Bir joker karakter dizesi.  
  
 `len`  
 En büyük uzunluğu `str` geçerli HString nesnesine atanmış parametresi.  
  
 `hstr`  
 Varolan bir HString nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString sınıfı](../windows/hstring-class.md)