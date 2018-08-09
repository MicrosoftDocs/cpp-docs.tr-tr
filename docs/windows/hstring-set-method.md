---
title: HString::Set yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
dev_langs:
- C++
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18ea9eafe3786d0a0df543cde654e1f0270dc8c7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011773"
---
# <a name="hstringset-method"></a>HString::Set Yöntemi
Geçerli değerini ayarlar **Hstrıng** belirtilen geniş karakter dizesini bir nesneye veya **Hstrıng** parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
  
### <a name="parameters"></a>Parametreler  
 *str*  
 Öğesinin geniş karakterli bir dizedir.  
  
 *Len*  
 En büyük uzunluğunu *str* geçerli atanan parametresi **Hstrıng** nesne.  
  
 *HSTR*  
 Mevcut bir **Hstrıng** nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)