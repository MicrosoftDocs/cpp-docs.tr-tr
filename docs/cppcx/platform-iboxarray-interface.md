---
title: Platform::IBoxArray arabirimi | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs: C++
helpviewer_keywords: Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 74afe390f91227a5ebad2246f9b2ad0f8c87a7de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray arabirimi
`IBoxArray`Uygulama ikili arabirimi (ABI) geçen veya koleksiyonları içinde depolanan değer türlerin dizileri için sarmalayıcı olan `Platform::Object^` gibi öğeler XAML denetimleri de.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Her dizi öğesi paketlenmiş değer türü.  
  
### <a name="remarks"></a>Açıklamalar  
 `IBoxArray`olan C + +/ CX adı `Windows::Foundation::IReferenceArray`.  
  
### <a name="members"></a>Üyeler  
 `IBoxArray` Arabirimi devraldığı `IValueType` arabirimi. `IBoxArray`Ayrıca bu üyeler vardır:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Değer](#value)|Bu konuda daha önce depolanan sarmalanmamış dizisi döndürür `IBoxArray` örneği.|  

## <a name="value"></a>IBoxArray::Value özelliği
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
 [Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)