---
title: Platform::MTAThreadAttribute sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 389767cdbd09cb5a2139b9302fc25fe02fb8a056
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757126"
---
# <a name="platformmtathreadattribute-class"></a>Platform::MTAThreadAttribute sınıfı
Bir uygulama için iş parçacığı modeli çok iş parçacıklı grup (MTA) olduğunu gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
public ref class MTAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MTAThreadAttribute Oluşturucusu 1](#ctor) Oluşturucusu|Sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
 MTAThreadAttribute özniteliğini devraldığı [Platform::Object sınıfı](../cppcx/platform-object-class.md). Ayrıca MTAThreadAttribute aşırı veya aşağıdaki üyeleri içerir:  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MTAThreadAttribute::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[MTAThreadAttribute::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|  
|[MTAThreadAttribute::ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Platform`  
  
### <a name="requirements"></a>Gereksinimler  
 **Meta veri:** platform.winmd  
  
 **Namespace:** platformu  



## <a name="ctor"></a> MTAThreadAttribute Oluşturucusu
MTAThreadAttribute sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:MTAThreadAttribute()  
```  
  


## <a name="equals"></a> MTAThreadAttribute::Equals
Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>Parametreler  
 obj  
 Karşılaştırma yapılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` nesneler eşit ise; Aksi takdirde, `false`.  
  


## <a name="gethashcode"></a> MTAThreadAttribute::GetHashCode
Bu örneğin karma kodunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örneğin karma kodu.  
  


## <a name="tostring"></a> MTAThreadAttribute::ToString
Geçerli nesneyi temsil eden bir dize döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesneyi temsil eden bir dize.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)