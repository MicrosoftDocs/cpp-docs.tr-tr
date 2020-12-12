---
description: 'Daha fazla bilgi edinin: CA2AEX Class'
title: CA2AEX sınıfı
ms.date: 11/04/2016
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
ms.openlocfilehash: 408e04760d6b614fd344b3cab1b34f22678db315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165114"
---
# <a name="ca2aex-class"></a>CA2AEX sınıfı

Bu sınıf, CA2TEX ve CT2AEX dize dönüştürme makroları ve typedef CA2A tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int t_nBufferLength = 128>
class CA2AEX
```

### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|Oluşturucu.|
|[CA2AEX:: ~ CA2AEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX:: operator LPSTR](#operator_lpstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|
|[CA2AEX:: m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde, kendi kodunuzda CA2TEX, CT2AEX veya CA2A kullanın.

Bu sınıf, dönüştürmenin sonucunu depolamak için kullanılan sabit boyutlu statik bir arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf, nesne kapsam dışına geçtiğinde bellek **malloc** kullanarak belleği ayırır. Bu, metin dönüştürme makrolarının önceki ATL sürümlerinde kullanılabilir olmasını sağlar, bu sınıfın Döngülerde kullanılması güvenlidir ve yığının taşmamasını sağlar.

Sınıf, yığın üzerinde bellek ayırmayı dener ve başarısız olursa, `AtlThrow` e_outofmemory bir bağımsız değişkeniyle çağrı yapılır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CA2TEX

- CT2AEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CA2A

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="ca2aexca2aex"></a><a name="ca2aex"></a> CA2AEX::CA2AEX

Oluşturucu.

```cpp
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Bu sınıfta kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Çeviri için gereken arabelleği oluşturur.

## <a name="ca2aexca2aex"></a><a name="dtor"></a> CA2AEX:: ~ CA2AEX

Yok edicisi.

```cpp
~CA2AEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="ca2aexm_psz"></a><a name="m_psz"></a> CA2AEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```cpp
LPSTR m_psz;
```

## <a name="ca2aexm_szbuffer"></a><a name="m_szbuffer"></a> CA2AEX:: m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```cpp
char m_szBuffer[ t_nBufferLength];
```

## <a name="ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a> CA2AEX:: operator LPSTR

Dönüştürme işleci.

```cpp
operator LPSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPSTR türünde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
