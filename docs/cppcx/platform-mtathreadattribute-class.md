---
title: "Platform::MTAThreadAttribute sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
dev_langs: C++
helpviewer_keywords: Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 6c45256272f7d72dd1da6b6486f9358eaf062b8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformmtathreadattribute-class"></a>Platform::MTAThreadAttribute sınıfı
İş parçacığı modeli bir uygulama için birden çok iş parçacıklı (MTA) olduğunu gösterir.  
  
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
 MTAThreadAttribute özniteliği devraldığı [Platform::Object sınıfı](../cppcx/platform-object-class.md). MTAThreadAttribute overloads ya da aşağıdaki üyeleri vardır:  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MTAThreadAttribute::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[MTAThreadAttribute::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|  
|[MTAThreadAttribute::ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Platform`  
  
### <a name="requirements"></a>Gereksinimler  
 **Meta veriler:** platform.winmd  
  
 **Namespace:** Platform  



## <a name="ctor"></a>MTAThreadAttribute Oluşturucusu
MTAThreadAttribute sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:MTAThreadAttribute()  
```  
  


## <a name="equals"></a>MTAThreadAttribute::Equals
Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>Parametreler  
 Obj  
 Karşılaştırma yapılacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`nesneleri eşitse; Aksi takdirde `false`.  
  


## <a name="gethashcode"></a>MTAThreadAttribute::GetHashCode
Bu örneğin karma kodunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örneğin karma kodu.  
  


## <a name="tostring"></a>MTAThreadAttribute::ToString
Geçerli nesneyi temsil eden bir dize döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesneyi temsil eden bir dize.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)