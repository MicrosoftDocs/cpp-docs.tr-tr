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
ms.openlocfilehash: 6da56e4d6c443520eb6f857624a5923e71a1e580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319002"
---
# <a name="catlexception-class"></a>CAtlException Sınıfı

Bu sınıf bir ATL özel durum tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CAtlException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException::operatör HRESULT](#operator_hresult)|Geçerli nesneyi bir HRESULT değerine atar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|Nesne tarafından oluşturulan ve hata koşulunu depolamak için kullanılan HRESULT türü değişkeni.|

## <a name="remarks"></a>Açıklamalar

Nesne, `CAtlException` Bir ATL işlemiyle ilgili bir özel durum koşulunu temsil eder. Sınıf, `CAtlException` özel durumun nedenini belirten durum kodunu depolayan bir genel veri üyesi ve özel durumu bir HRESULT'muş gibi ele almanızı sağlayan bir döküm işleci içerir.

Genel olarak, doğrudan `AtlThrow` bir `CAtlException` nesne oluşturmak yerine çağırırsınız.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlexcept.h

## <a name="catlexceptioncatlexception"></a><a name="catlexception"></a>CAtlException::CAtlException

Oluşturucu.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parametreler

*Hr*<br/>
HRESULT hata kodu.

## <a name="catlexceptionoperator-hresult"></a><a name="operator_hresult"></a>CAtlException::operatör HRESULT

Geçerli nesneyi bir HRESULT değerine atar.

```
operator HRESULT() const throw ();
```

## <a name="catlexceptionm_hr"></a><a name="m_hr"></a>CAtlException::m_hr

HRESULT veri üyesi.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Açıklamalar

Hata durumunu depolayan veri üyesi. HRESULT değeri oluşturucu, [CAtlException::CAtlException](#catlexception)tarafından ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Atlthrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
