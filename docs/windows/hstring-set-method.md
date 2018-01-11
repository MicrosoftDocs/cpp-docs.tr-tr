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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5919e1d0247cb8af17d98b7de97c33484be2128f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [HString Sınıfı](../windows/hstring-class.md)