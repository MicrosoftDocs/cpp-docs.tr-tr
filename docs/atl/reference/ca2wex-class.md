---
title: CA2WEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9ac0528f383f1d379699c153a87507a1a292e21
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767510"
---
# <a name="ca2wex-class"></a>CA2WEX sınıfı

Bu sınıf, dize dönüşüm makroları CA2TEX, CA2CTEX, CT2WEX ve CT2CWEX ve typedef CA2W tarafından kullanılır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*  
Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|Oluşturucu.|
|[CA2WEX:: ~ CA2WEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|
|[CA2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.|

## <a name="remarks"></a>Açıklamalar

Ek işlevler gerekmiyorsa CA2TEX, CA2CTEX, CT2WEX, CT2CWEX veya CA2W kodunuzda kullanın.

Bu sınıf, dönüştürmenin sonucu depolamak için kullanılan sabit boyutlu bir statik arabellek içerir. Sonucu statik arabelleğe sığamayacak kadar büyük olursa, sınıfı kullanarak bellek ayırır **malloc**, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıf Döngülerde güvenlidir ve stack overflow olmaz sağlar.

Sınıfı başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` E_OUTOFMEMORY bağımsız.

Varsayılan olarak, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için ATL dönüştürme sınıfları ve makroları kullanın. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, kod sayfası sınıfı için oluşturucu ikinci parametre olarak belirtin.

Aşağıdaki makroları bu sınıfa bağlıdır:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Aşağıdaki tür tanımı bu sınıfa bağlıdır:

- CA2W

Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlconv.h

##  <a name="ca2wex"></a>  CA2WEX::CA2WEX

Oluşturucu.

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*psz*  
Dönüştürülecek metin dizesi.

*nCodePage*  
Dönüştürme gerçekleştirmek için kullanılan kod sayfası. Windows SDK'sı işlevi için kod sayfası parametresi tartışmalara bakın [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar) daha fazla ayrıntı için.

### <a name="remarks"></a>Açıklamalar

Çeviri işlemde kullanılan arabellek ayırır.

##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX

Yıkıcı.

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılmış ara belleğini serbest bırakır.

##  <a name="m_psz"></a>  CA2WEX::m_psz

Kaynak dizesi depolar veri üyesi.

```
LPWSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer

Dönüştürülmüş dize depolamak için kullanılan statik arabelleği.

```
wchar_t m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpwstr"></a>  CA2WEX::operator LPWSTR

Dönüştürme işleci.

```  
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesi, LPWSTR olarak döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
[CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
[CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
[CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
