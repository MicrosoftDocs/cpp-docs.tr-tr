---
title: CManualAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
ms.openlocfilehash: 526415f14172911b26462fab97d9e0a7513b8cad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62231070"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor Sınıfı

Gelişmiş kullanım için tasarlanmış bir erişimci türünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CManualAccessor : public CAccessorBase
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddBindEntry](#addbindentry)|Bir bağlama giriş çıkış sütunları ekler.|
|[AddParameterEntry](#addparameterentry)|Parametre erişimcisi için bir parametre girişi ekler.|
|[CreateAccessor](#createaccessor)|Bağlama yapıları sütun için bellek ayırır ve sütun veri üyelerine başlatır.|
|[CreateParameterAccessor](#createparameteraccessor)|Bağlama yapıları parametresi için bellek ayırır ve parametre veri üyeleri başlatır.|

## <a name="remarks"></a>Açıklamalar

Kullanarak `CManualAccessor`, parametresini belirtin ve çalışma zamanı işlev çağrıları çıktı sütunu bağlaması.

## <a name="addbindentry"></a> CManualAccessor::AddBindEntry

Bir bağlama giriş çıkış sütunları ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void AddBindEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL) throw ();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IAccessor::CreateAccessor'ı](/previous-versions/windows/desktop/ms716845(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

*nOrdinal*<br/>
[in] Sütun numarası.

*wType*<br/>
[in] Veri türü.

*nColumnSize*<br/>
[in] Sütun boyutu bayt cinsinden.

*pData*<br/>
[in] Arabellekteki depolanan sütun verileri için bir işaretçi.

*pLength*<br/>
[in] Alan uzunluğu gerekirse bir işaretçi.

*pStatus*<br/>
[in] Gerekirse sütun durumuna bağlı değişken bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmak için öncelikle çağırmalısınız [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Belirtilen sütun sayısından daha fazla giriş eklenemiyor `CreateAccessor`.

## <a name="addparameterentry"></a> CManualAccessor::AddParameterEntry

Bir parametre girişi parametre girişi yapılara ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void AddParameterEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL,
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();
```

#### <a name="parameters"></a>Parametreler

Bkz: [IAccessor::CreateAccessor'ı](/previous-versions/windows/desktop/ms716845(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

*nOrdinal*<br/>
[in] Parametre numarası.

*wType*<br/>
[in] Veri türü.

*nColumnSize*<br/>
[in] Sütun boyutu bayt cinsinden.

*pData*<br/>
[in] Arabellekteki depolanan sütun verileri için bir işaretçi.

*pLength*<br/>
[in] Alan uzunluğu gerekirse bir işaretçi.

*pStatus*<br/>
[in] Gerekirse sütun durumuna bağlı değişken bir işaretçi.

*eParamIO*<br/>
[in] Parametre bağlama ilişkili olduğu bir giriş, giriş/çıkış veya çıkış parametresi olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmak için öncelikle çağırmalısınız [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).

## <a name="createaccessor"></a> CManualAccessor::CreateAccessor

Bağlama yapıları sütun için bellek ayırır ve sütun veri üyelerine başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CreateAccessor(int nBindEntries,
  void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Parametreler

*nBindEntries*<br/>
[in] Sütun sayısı. Bu sayı, yapılan çağrı sayısı eşleşmelidir [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) işlevi.

*pBuffer*<br/>
[in] Çıktı sütunları depolandığı arabellek için işaretçi.

*nBufferSize*<br/>
[in] Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Çağırmadan önce bu işlevi çağırın `CManualAccessor::AddBindEntry` işlevi.

## <a name="createparameteraccessor"></a> CManualAccessor::CreateParameterAccessor

Bağlama yapıları parametresi için bellek ayırır ve parametre veri üyeleri başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CreateParameterAccessor(int nBindEntries,
   void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Parametreler

*nBindEntries*<br/>
[in] Sütun sayısı.

*pBuffer*<br/>
[in] Giriş sütunları depolandığı arabellek için işaretçi.

*nBufferSize*<br/>
[in] Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Çağırmadan önce bu işlevi çağırmanız gerekir [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md).

## <a name="see-also"></a>Ayrıca bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)