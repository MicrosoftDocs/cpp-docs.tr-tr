---
title: Platform::IBox arabirimi | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed15a372fcb8cc72d2ad9aa1ce856470da0126b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformibox-interface"></a>Platform::IBox arabirimi
[Platform::IBox](../cppcx/platform-ibox-interface.md) arabirimi için C++ adıdır `Windows::Foundation::IReference` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Paketlenmiş değer türü.  
  
### <a name="remarks"></a>Açıklamalar  
 `IBox<T>` Arabirimi öncelikle dahili olarak kullanılan boş değer atanabilen değer türleri temsil etmek için açıklandığı gibi [değer sınıflar ve yapılar (C + +/ CX)](../cppcx/value-classes-and-structs-c-cx.md). Arabirim türünde parametre almayan C++ yöntemlere iletilen kutusunu değer türleri için de kullanılır `Object^`. Giriş parametresi olarak açıkça bildirebilir `IBox<SomeValueType>`. Bir örnek için bkz: [kutulama](../cppcx/boxing-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
  
### <a name="members"></a>Üyeler  
 `Platform::IBox` Arabirimi devraldığı [Platform::IValueType](../cppcx/platform-ivaluetype-interface.md) arabirimi. `IBox` Bu üyeler vardır:  
  
 **Özellikler**  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Değer](#value)|Bu konuda daha önce depolanan sarmalanmamış değeri döndürür `IBox` örneği.|  

## <a name="value"></a> IBox::Value özelliği
Bu nesne depolanan değeri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Paketlenmiş değer türü.  
  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bu nesne depolanan değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir örnek için bkz: [kutulama](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)