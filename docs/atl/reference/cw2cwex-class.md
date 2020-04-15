---
title: CW2CWEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 07dd0319586054403d8ed0c8efc813b4061e355a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330442"
---
# <a name="cw2cwex-class"></a>CW2CWEX Sınıfı

Bu sınıf dize dönüştürme makroları CW2CTEX ve CT2CWEX ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|Oluşturucu.|
|[CW2CWEX::~CW2CWEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CW2CWEX::operatör LPCWSTR](#operator_lpcwstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kodunuzda CW2CTEX, CT2CWEX veya CW2W kullanın.

Bu sınıfın döngüler halinde kullanımı güvenlidir ve yığını taşmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayanır:

- CW2CTEX

- CT2CWEX

Aşağıdaki typedef bu sınıfa dayanır:

- CW2W

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX

Oluşturucu.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX::~CW2CWEX

Yıkıcı.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a>CW2CWEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX::operatör LPCWSTR

Dönüşüm işleci.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPCWSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
