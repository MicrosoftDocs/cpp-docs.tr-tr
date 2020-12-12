---
description: 'Hakkında daha fazla bilgi edinin: cancellation_token_registration sınıfı'
title: cancellation_token_registration Sınıfı
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: 1901e5132a9bad6849b1b00a6be63caf9afc9170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172147"
---
# <a name="cancellation_token_registration-class"></a>cancellation_token_registration Sınıfı

`cancellation_token_registration`Sınıfı, bir geri çağırma bildirimini temsil eder `cancellation_token` . `register`Bir üzerinde yöntemi, `cancellation_token` İptalin ne zaman yapıldığını belirten bir bildirim almak için kullanıldığında, `cancellation_token_registration` çağıran belirli bir geri çağırma işlemini daha sonra metodun kullanımı ile isteyebilmesi için bir nesne geri aramaya bir tanıtıcı olarak döndürülür `deregister` .

## <a name="syntax"></a>Syntax

```cpp
class cancellation_token_registration;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration yok edici](#dtor)||

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](#operator_neq)||
|[işleç =](#operator_eq)||
|[işleç = =](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`cancellation_token_registration`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** pplcancellation_token. h

**Ad alanı:** eşzamanlılık

## <a name="cancellation_token_registration"></a><a name="dtor"></a> ~ cancellation_token_registration

```cpp
~cancellation_token_registration();
```

## <a name="cancellation_token_registration"></a><a name="ctor"></a> cancellation_token_registration

```cpp
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
`cancellation_token_registration`Kopyalanacak veya taşınacak.

## <a name="operator"></a><a name="operator_neq"></a> işleç! =

```cpp
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
`cancellation_token_registration`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_eq"></a> işleç =

```cpp
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
`cancellation_token_registration`Atanacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_eq_eq"></a> işleç = =

```cpp
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
`cancellation_token_registration`Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
