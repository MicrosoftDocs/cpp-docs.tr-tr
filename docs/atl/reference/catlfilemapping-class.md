---
title: CAtlFileMapping Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: ca46ccdacf5ea24f1de26cdc75bf808c4ecfaa40
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318953"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping Sınıfı

Bu sınıf, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)yöntemlerine bir döküm işleci ekleyerek, bellek eşlenen bir dosyayı temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Döküm işleci için kullanılan veri türü.

## <a name="members"></a>Üyeler

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMapping::operatör T*](#operator_t_star)|Nesnelerin örtülü `CAtlFileMapping` olarak ' `T*`a dönüştürülmesine izin verir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CAtlFileMapping` nesnelerin örtülü olarak . `T*` Diğer üyeler taban sınıf, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)tarafından sağlanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Catlfilemappingbase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile.h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping::operatör T*

Nesnelerin örtülü `CAtlFileMapping` olarak ' `T*`a dönüştürülmesine izin verir.

```
operator T*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek `T*` eşlenen dosyanın başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlFileMappingBase'i çağırır::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) ve döndürülen `T*` işaretçiyi, bu sınıfın şablon parametresi olarak kullanılan *T* türü olarak yeniden yorumlar.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMappingBase Sınıfı](../../atl/reference/catlfilemappingbase-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
