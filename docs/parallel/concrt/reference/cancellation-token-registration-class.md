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
ms.openlocfilehash: cf803fbd35071a7a7100e3267dcf1bfa8b91e9f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059608"
---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration Sınıfı
`cancellation_token_registration` Sınıfı temsil eden bir geri çağırma bildiriminden bir `cancellation_token`. Zaman `register` metodunda bir `cancellation_token` gerçekleşen iptal bildirimi almak için kullanılan bir `cancellation_token_registration` çağıran özel bir geri çağırma artık isteyebilmesi için geri çağırma tanıtıcı kullanarakyapılmasıgibinesnedöndürülür`deregister` yöntemi.  
  
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
*_Src*<br/>
`cancellation_token_registration` Kopyalamak veya taşımak için.
 
##  <a name="operator_neq"></a> işleç! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Rhs*<br/>
`cancellation_token_registration` Karşılaştırmak için.
 
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a> işleç = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>Parametreler  
*_Src*<br/>
`cancellation_token_registration` Atamak için.
 
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq_eq"></a> işleç == 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>Parametreler  
*_Rhs*<br/>
`cancellation_token_registration` Karşılaştırmak için.
 
### <a name="return-value"></a>Dönüş Değeri  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
