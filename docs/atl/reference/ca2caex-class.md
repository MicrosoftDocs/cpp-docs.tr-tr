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
ms.openlocfilehash: 505c1e369bc5949fea291a2172c16d5e52c75567
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168520"
---
# <a name="ca2caex-class"></a>CA2CAEX Sınıfı

Bu sınıf, CA2CTEX ve CT2CAEX dize dönüştürme makroları ve typedef CA2CA tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template<int t_nBufferLength = 128>
class CA2CAEX
```

### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|Oluşturucu.|
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX:: operator LPCSTR](#operator_lpcstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CA2CAEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde, kendi kodunuzda CA2CTEX, CT2CAEX veya CA2CA kullanın.

Bu sınıfın Döngülerde kullanılması güvenlidir ve yığın taşmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CA2CTEX

- CT2CAEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CA2CA

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

Oluşturucu.

```cpp
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Bu sınıfta kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Çeviri için gereken arabelleği oluşturur.

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX:: ~ CA2CAEX

Yok edicisi.

```cpp
~CA2CAEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```cpp
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX:: operator LPCSTR

Dönüştürme işleci.

```cpp
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
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
