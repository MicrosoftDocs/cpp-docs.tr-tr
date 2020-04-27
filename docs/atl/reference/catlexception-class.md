---
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
ms.openlocfilehash: f09d9b2f46233cf356f5ade8a5b90e08a213d276
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168208"
---
# <a name="catlexception-class"></a>CAtlException Sınıfı

Bu sınıf, ATL özel durumunu tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException:: CAtlException](#catlexception)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException:: operator HRESULT](#operator_hresult)|Geçerli nesneyi bir HRESULT değerine yayınlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException:: m_hr](#m_hr)|Nesne tarafından oluşturulan ve hata koşulunu depolamak için kullanılan HRESULT türündeki değişken.|

## <a name="remarks"></a>Açıklamalar

Bir `CAtlException` nesne, ATL işlemiyle ilgili bir özel durum koşulunu temsil eder. `CAtlException` Sınıfı, özel durumun nedenini belirten bir genel veri üyesini ve özel durumu HRESULT gibi değerlendirmesine izin veren bir atama işlecini içerir.

Genel olarak, doğrudan bir `AtlThrow` `CAtlException` nesne oluşturmak yerine çağıracaksınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlexcept. h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>CAtlException:: CAtlException

Oluşturucu.

```cpp
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parametreler

*HR*<br/>
HRESULT hata kodu.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException:: operator HRESULT

Geçerli nesneyi bir HRESULT değerine yayınlar.

```cpp
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>CAtlException:: m_hr

HRESULT veri üyesi.

```cpp
HRESULT m_hr;
```

### <a name="remarks"></a>Açıklamalar

Hata koşulunu depolayan veri üyesi. HRESULT değeri, Oluşturucu tarafından ayarlanır, [CAtlException:: CAtlException](#catlexception).

## <a name="see-also"></a>Ayrıca bkz.

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
