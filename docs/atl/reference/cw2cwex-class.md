---
description: 'Daha fazla bilgi edinin: CW2CWEX Class'
title: CW2CWEX sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
ms.openlocfilehash: 769dcedf1a9dc15129b09e3305330de33242562e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140237"
---
# <a name="cw2cwex-class"></a>CW2CWEX sınıfı

Bu sınıf, CW2CTEX ve CT2CWEX dize dönüştürme makroları ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|Oluşturucu.|
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX:: operator LPCWSTR](#operator_lpcwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde kodunuzda CW2CTEX, CT2CWEX veya CW2W kullanın.

Bu sınıfın Döngülerde kullanılması güvenlidir ve yığın taşmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CW2CTEX

- CT2CWEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CW2W

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="cw2cwexcw2cwex"></a><a name="cw2cwex"></a> CW2CWEX::CW2CWEX

Oluşturucu.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="cw2cwexcw2cwex"></a><a name="dtor"></a> CW2CWEX:: ~ CW2CWEX

Yok edicisi.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="cw2cwexm_psz"></a><a name="m_psz"></a> CW2CWEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```
LPCWSTR m_psz;
```

## <a name="cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a> CW2CWEX:: operator LPCWSTR

Dönüştürme işleci.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPCWSTR türünde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
