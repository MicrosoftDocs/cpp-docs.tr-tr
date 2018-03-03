---
title: "İşleç&lt; işleç (Microsoft::WRL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
dev_langs:
- C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fca41cae7c8fdadd215b049228da0b87788d2717
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="operatorlt-operator-microsoftwrl"></a>İşleç&lt; işleç (Microsoft::WRL)
Bir nesnenin adresi başka bir değerden olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<class T, class U>  
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();  
template<class T, class U>  
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `a`  
 Sol nesnesi.  
  
 `b`  
 Doğru nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`varsa adresini `a` adresini'dan küçük `b`; Aksi halde, `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)