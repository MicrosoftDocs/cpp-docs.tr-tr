---
title: Platform::ıbox arabirimi | Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d83afb854aaa400a02f9de95e269f85cfeba1a96
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586878"
---
# <a name="platformibox-interface"></a>Platform::ıbox arabirimi
[Platform::ıbox](../cppcx/platform-ibox-interface.md) arabirimi için C++ addır `Windows::Foundation::IReference` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T>  
interface class IBox  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Paketlenmiş değer türü.  
  
### <a name="remarks"></a>Açıklamalar  
 `IBox<T>` Arabirimi öncelikle dahili olarak kullanılan boş değer atanabilen değer türleri temsil etmek için açıklandığı [değer sınıfları ve yapıları (C + +/ CX)](../cppcx/value-classes-and-structs-c-cx.md). Parametre türü C++ yöntemlere iletilen kutusu değer türleri için de arabirimi kullanılır `Object^`. Giriş parametresi olarak açıkça bildirebilirsiniz `IBox<SomeValueType>`. Bir örnek için bkz. [kutulama](../cppcx/boxing-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
  
### <a name="members"></a>Üyeler  
 `Platform::IBox` Arabirimi devralır [Platform::ıvaluetype](../cppcx/platform-ivaluetype-interface.md) arabirimi. `IBox` Bu üyeleri içerir:  
  
 **Özellikler**  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Değer](#value)|Bu konuda daha önce depolanan kutulanmamış değer döndürür `IBox` örneği.|  

## <a name="value"></a> IBox::Value özelliği
Bu nesnesinde depolanan değeri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Paketlenmiş değer türü.  
  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bu nesnesinde depolanan değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir örnek için bkz. [kutulama](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)