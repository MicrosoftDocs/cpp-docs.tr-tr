---
title: Platform::IBox arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
ms.assetid: 774df45d-f8a7-45a3-ae24-eecc3c681040
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7894eceb2f345303400eec9b0490db58b3c3583f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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