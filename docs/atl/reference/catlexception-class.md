---
description: 'Daha fazla bilgi edinin: CAtlException Sınıfı'
title: CAtlException Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: b6d788bc8d852fa0b8d091682ff7740aa4ebbbed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147478"
---
# <a name="catlexception-class"></a>CAtlException Sınıfı

Bu sınıf, ATL özel durumunu tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class CAtlException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException:: CAtlException](#catlexception)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException:: operator HRESULT](#operator_hresult)|Geçerli nesneyi bir HRESULT değerine yayınlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException:: m_hr](#m_hr)|Nesne tarafından oluşturulan ve hata koşulunu depolamak için kullanılan HRESULT türündeki değişken.|

## <a name="remarks"></a>Açıklamalar

Bir `CAtlException` nesne, ATL işlemiyle ilgili bir özel durum koşulunu temsil eder. `CAtlException`Sınıfı, özel durumun nedenini belirten bir genel veri üyesini ve özel durumu HRESULT gibi değerlendirmesine izin veren bir atama işlecini içerir.

Genel olarak, `AtlThrow` doğrudan bir nesne oluşturmak yerine çağıracaksınız `CAtlException` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlexcept. h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a> CAtlException:: CAtlException

Oluşturucu.

```cpp
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parametreler

*sa*<br/>
HRESULT hata kodu.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a> CAtlException:: operator HRESULT

Geçerli nesneyi bir HRESULT değerine yayınlar.

```cpp
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a> CAtlException:: m_hr

HRESULT veri üyesi.

```cpp
HRESULT m_hr;
```

### <a name="remarks"></a>Açıklamalar

Hata koşulunu depolayan veri üyesi. HRESULT değeri, Oluşturucu tarafından ayarlanır, [CAtlException:: CAtlException](#catlexception).

## <a name="see-also"></a>Ayrıca bkz.

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
