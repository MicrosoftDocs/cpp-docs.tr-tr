---
title: CA2CAEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: e6c727993b2907aaa551421a5d2d23e372b68917
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319141"
---
# <a name="ca2caex-class"></a>CA2CAEX Sınıfı

Bu sınıf dize dönüştürme makroları CA2CTEX ve CT2CAEX ve typedef CA2CA tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|Oluşturucu.|
|[CA2CAEX::~CA2CAEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX::operatör LPCSTR](#operator_lpcstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kendi kodunuzda CA2CTEX, CT2CAEX veya CA2CA kullanın.

Bu sınıfın döngüler halinde kullanımı güvenlidir ve yığını taşmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayanır:

- CA2CTEX

- CT2CAEX

Aşağıdaki typedef bu sınıfa dayanır:

- CA2CA

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

Oluşturucu.

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Bu sınıfta kullanılmayan.

### <a name="remarks"></a>Açıklamalar

Çeviri için gerekli arabelleği oluşturur.

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX::~CA2CAEX

Yıkıcı.

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX::operatör LPCSTR

Dönüşüm işleci.

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPCSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
