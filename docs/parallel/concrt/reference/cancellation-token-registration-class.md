---
title: cancellation_token_registration sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe11e2697734d06988f4cbcfce48f38cf02c32b7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration Sınıfı
`cancellation_token_registration` Sınıfı temsil eden bir geri çağırma bildirimden bir `cancellation_token`. Zaman `register` yöntemi bir `cancellation_token` iptal oluştuğunda, bildirimi almak için kullanılan bir `cancellation_token_registration` nesne çağıran artık belirli bir geri çağırma istemesini geri dönüş için bir tanıtıcı kullanımlayapılmasıgibidöndürülür`deregister` yöntemi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[cancellation_token_registration](#ctor)||  
|[~ cancellation_token_registration yok Edicisi](#dtor)||  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** pplcancellation_token.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="ctor"></a> cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
##  <a name="operator_neq"></a> operator! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Src`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> operator == 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
