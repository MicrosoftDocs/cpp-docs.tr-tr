---
title: "Platform::STAThreadAttribute sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs: C++
helpviewer_keywords: Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c2b8c38d672b6bd3ecd0fcafb54a9b6e723202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute sınıfı
Bir uygulama için iş parçacığı modelini tek iş parçacıklı (STA) olduğunu gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[STAThreadAttribute Oluşturucusu 1](#ctor)|Sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
 STAThreadAttribute özniteliği devraldığı [Platform::Object sınıfı](../cppcx/platform-object-class.md). STAThreadAttribute overloads ya da aşağıdaki üyeleri vardır:  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|  
|[STAThreadAttribute::ToString](#tostring)|Geçerli nesneyi temsil eden bir dize döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Platform`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform  



## <a name="ctor"></a>STAThreadAttribute Oluşturucusu
STAThreadAttribute sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a>STAThreadAttribute::Equals
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
  


## <a name="gethashcode"></a>STAThreadAttribute::GetHashCode
Bu örneğin karma kodunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örneğin karma kodu.  
  


## <a name="tostring"></a>STAThreadAttribute::ToString
Geçerli nesneyi temsil eden bir dize döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesneyi temsil eden bir dize.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)