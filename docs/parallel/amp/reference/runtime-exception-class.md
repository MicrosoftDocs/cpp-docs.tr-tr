---
title: runtime_exception sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff10cb3958ffa82e3ef2bb70d8370d1a52c4a929
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695752"
---
# <a name="runtimeexception-class"></a>runtime_exception Sınıfı
C++ hızlandırılmış yoğun paralellik (AMP) Kitaplığı'nda özel durumlar için temel türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[runtime_exception Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `runtime_exception` sınıfı.|  
|[~ runtime_exception yok Edicisi](#dtor)|Bozar `runtime_exception` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|Özel duruma neden hata kodunu döndürür.|  

  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `runtime_exception` bunu nesnesine.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amprt.h  
  
 **Namespace:** eşzamanlılık  

## <a name="runtime_exception__ctor"></a>  runtime_exception Oluşturucusu  
Sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Message`  
 Özel duruma neden hata açıklaması.  
  
 `_Hresult`  
 Özel duruma neden hata HRESULT.  
  
 `_Other`  
 `runtime_exception` Kopyalamak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `runtime_exception` Nesnesi.  

## <a name="dtor"></a>  ~ runtime_exception yok Edicisi  
Nesne yok eder.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>  get_error_code   
Özel duruma neden hata kodunu döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özel duruma neden hata HRESULT.  
  
## <a name="runtime_exception__operator_eq"></a>  işleç =   
  Belirtilen içeriğini kopyalar `runtime_exception` bunu nesnesine.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `runtime_exception` Kopyalamak için nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `runtime_exception` nesnesi.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
