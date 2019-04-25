---
title: CW2WEX sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: d6d68f4f5c0f3532c39fee3f513e7b3102ec075d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277142"
---
# <a name="cw2wex-class"></a>CW2WEX sınıfı

Bu sınıf, dize dönüşüm makroları CW2TEX ve CT2WEX ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|Oluşturucu.|
|[CW2WEX::~CW2WEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|
|[CW2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.|

## <a name="remarks"></a>Açıklamalar

Ek işlevler gerekmiyorsa CW2TEX, CT2WEX veya CW2W kodunuzda kullanın.

Bu sınıf, dönüştürmenin sonucu depolamak için kullanılan sabit boyutlu bir statik arabellek içerir. Sonucu statik arabelleğe sığamayacak kadar büyük olursa, sınıfı kullanarak bellek ayırır **malloc**, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıf Döngülerde güvenlidir ve stack overflow olmaz sağlar.

Sınıfı başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` E_OUTOFMEMORY bağımsız.

Varsayılan olarak, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için ATL dönüştürme sınıfları ve makroları kullanın.

Aşağıdaki makroları bu sınıfa bağlıdır:

- CW2TEX

- CT2WEX

Aşağıdaki tür tanımı bu sınıfa bağlıdır:

- CW2W

Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlconv.h

##  <a name="cw2wex"></a>  CW2WEX::CW2WEX

Oluşturucu.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Çeviri için gerekli arabellek oluşturur.

##  <a name="dtor"></a>  CW2WEX:: ~ CW2WEX

Yok edici...

```
~CW2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılmış ara belleğini serbest bırakır.

##  <a name="m_psz"></a>  CW2WEX::m_psz

Kaynak dizesi depolar veri üyesi.

```
LPWSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CW2WEX::m_szBuffer

Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.

```
wchar_t m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpwstr"></a>  CW2WEX::operator LPWSTR

Atama işleci.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesi, LPWSTR olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
