---
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
ms.openlocfilehash: 712e663ab58e2c9de4e2f25090b84b35d0bced71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247644"
---
# <a name="ca2aex-class"></a>CA2AEX sınıfı

Bu sınıf, dize dönüşüm makroları CA2TEX ve CT2AEX ve typedef CA2A tarafından kullanılır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|Oluşturucu.|
|[CA2AEX::~CA2AEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX::operator LPSTR](#operator_lpstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|
|[CA2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.|

## <a name="remarks"></a>Açıklamalar

Ek işlevler gerekmiyorsa, kendi kodunuzda CA2TEX, CT2AEX veya CA2A kullanın.

Bu sınıf, dönüştürmenin sonucu depolamak için kullanılan sabit boyutlu bir statik arabellek içerir. Sonucu statik arabelleğe sığamayacak kadar büyük olursa, sınıfı kullanarak bellek ayırır **malloc**, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıf Döngülerde güvenlidir ve stack overflow olmaz sağlar.

Sınıfı başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` E_OUTOFMEMORY bağımsız.

Varsayılan olarak, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için ATL dönüştürme sınıfları ve makroları kullanın.

Aşağıdaki makroları bu sınıfa bağlıdır:

- CA2TEX

- CT2AEX

Aşağıdaki tür tanımı bu sınıfa bağlıdır:

- CA2A

Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlconv.h

##  <a name="ca2aex"></a>  CA2AEX::CA2AEX

Oluşturucu.

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Bu sınıftaki kullanılmayan.

### <a name="remarks"></a>Açıklamalar

Çeviri için gerekli arabellek oluşturur.

##  <a name="dtor"></a>  CA2AEX::~CA2AEX

Yıkıcı.

```
~CA2AEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılmış ara belleğini serbest bırakır.

##  <a name="m_psz"></a>  CA2AEX::m_psz

Kaynak dizesi depolar veri üyesi.

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer

Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.

```
char m_szBuffer[ t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CA2AEX::operator LPSTR

Dönüştürme işleci.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesi LPSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
