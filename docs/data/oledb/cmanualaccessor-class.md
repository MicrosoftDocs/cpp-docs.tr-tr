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
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
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
ms.openlocfilehash: 80c8f94a417c700f86159de53bd53e4011f78d71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447379"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor Sınıfı

Gelişmiş kullanım için tasarlanan bir erişimci türünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CManualAccessor : public CAccessorBase
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddBindEntry](#addbindentry)|Çıkış sütunlarına bir bağlama girişi ekler.|
|[AddParameterEntry](#addparameterentry)|Parametre erişimcisine bir parametre girişi ekler.|
|[CreateAccessor](#createaccessor)|Sütun bağlama yapıları için bellek ayırır ve sütun veri üyelerini başlatır.|
|[CreateParameterAccessor](#createparameteraccessor)|Parametre bağlama yapıları için bellek ayırır ve parametre veri üyelerini başlatır.|

## <a name="remarks"></a>Açıklamalar

`CManualAccessor`kullanarak, çalışma zamanı işlev çağrılarının parametresini ve çıkış sütunu bağlamayı belirtebilirsiniz.

## <a name="addbindentry"></a>CManualAccessor:: AddBindEntry

Çıkış sütunlarına bir bağlama girişi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void AddBindEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL) throw ();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Sütun numarası.

*wType*<br/>
'ndaki Veri türü.

*nColumnSize*<br/>
'ndaki Bayt cinsinden sütun boyutu.

*pData*<br/>
'ndaki Arabellekte depolanan sütun verilerine yönelik bir işaretçi.

*pLength*<br/>
'ndaki Gerekirse alan uzunluğuna yönelik bir işaretçi.

*pStatus*<br/>
'ndaki Gerekirse, sütun durumuna bağlanacak değişkene yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmak için, önce [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)öğesini çağırmanız gerekir. `CreateAccessor`belirtilen sütun sayısından daha fazla giriş ekleyemezsiniz.

## <a name="addparameterentry"></a>CManualAccessor:: AddParameterEntry

Parametre girişi yapılarına bir parametre girişi ekler.

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

*OLE DB Programcı başvurusunda* [dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) bölümüne bakın.

*nOrdinal*<br/>
'ndaki Parametre numarası.

*wType*<br/>
'ndaki Veri türü.

*nColumnSize*<br/>
'ndaki Bayt cinsinden sütun boyutu.

*pData*<br/>
'ndaki Arabellekte depolanan sütun verilerine yönelik bir işaretçi.

*pLength*<br/>
'ndaki Gerekirse alan uzunluğuna yönelik bir işaretçi.

*pStatus*<br/>
'ndaki Gerekirse, sütun durumuna bağlanacak değişkene yönelik bir işaretçi.

*Eparaıo*<br/>
'ndaki Bağlamanın ilişkili olduğu parametrenin bir giriş, giriş/çıkış veya çıkış parametresi olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmak için, ilk olarak [CreateParameterAccessor yöntemini](../../data/oledb/cmanualaccessor-createparameteraccessor.md)çağırmanız gerekir.

## <a name="createaccessor"></a>CManualAccessor:: CreateAccessor

Sütun bağlama yapıları için bellek ayırır ve sütun veri üyelerini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CreateAccessor(int nBindEntries,
  void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Parametreler

*Nbindendenemeler*<br/>
'ndaki Sütun sayısı. Bu sayı, [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) işlevine yapılan çağrı sayısıyla eşleşmelidir.

*pBuffer*<br/>
'ndaki Çıktı sütunlarının depolandığı arabelleğin bir işaretçisi.

*nBufferSize*<br/>
'ndaki Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`CManualAccessor::AddBindEntry` işlevini çağırmadan önce bu işlevi çağırın.

## <a name="createparameteraccessor"></a>CManualAccessor:: CreateParameterAccessor

Parametre bağlama yapıları için bellek ayırır ve parametre veri üyelerini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CreateParameterAccessor(int nBindEntries,
   void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Parametreler

*Nbindendenemeler*<br/>
'ndaki Sütun sayısı.

*pBuffer*<br/>
'ndaki Giriş sütunlarının depolandığı arabelleğin işaretçisi.

*nBufferSize*<br/>
'ndaki Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)çağrılmadan önce bu işlevi çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)