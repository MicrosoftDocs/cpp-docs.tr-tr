---
title: CAtlException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56038ffe4c6062422ea34a439e73b0d90a37cfb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097737"
---
# <a name="catlexception-class"></a>CAtlException sınıfı

Bu sınıf, ATL istisna tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CAtlException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException::operator HRESULT](#operator_hresult)|HRESULT değerini geçerli nesneye çevirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|Türünde değişken HRESULT nesne tarafından oluşturulan ve hata durumunu depolamak için kullanılır.|

## <a name="remarks"></a>Açıklamalar

A `CAtlException` nesnesi bir ATL işlemiyle ilgili bir özel durum koşulunu temsil eder. `CAtlException` Sınıfı özel durumu ve HRESULT değilmiş gibi özel durumu işle olanak tanıyan bir atama işleci nedenini gösteren durum kodunu depolar genel veri üyesi içerir.

Genel olarak, çağıracak `AtlThrow` oluşturmak yerine bir `CAtlException` doğrudan nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlexcept.h

##  <a name="catlexception"></a>  CAtlException::CAtlException

Oluşturucu.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
HRESULT hata kodu.

##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT

HRESULT değerini geçerli nesneye çevirir.

```
operator HRESULT() const throw ();
```

##  <a name="m_hr"></a>  CAtlException::m_hr

HRESULT veri üyesi.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Açıklamalar

Hata koşulu depolar veri üyesi. HRESULT değerini Oluşturucu tarafından ayarlanan [CAtlException::CAtlException](#catlexception).

## <a name="see-also"></a>Ayrıca Bkz.

[Çeşitlemeleri](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
