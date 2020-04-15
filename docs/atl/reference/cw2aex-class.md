---
title: CW2AEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 849cbe5c26d7c7af7a8925a26057b5777554471d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330447"
---
# <a name="cw2aex-class"></a>CW2AEX Sınıfı

Bu sınıf dize dönüştürme makroları CT2AEX, CW2TEX, CW2CTEX ve CT2CAEX ve typedef CW2A tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Oluşturucu.|
|[CW2AEX::~CW2AEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CW2AEX::operatör LPSTR](#operator_lpstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|
|[CW2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kodunuzda CT2AEX, CW2TEX, CW2CTEX, CT2CAEX veya CW2A kullanın.

Bu sınıf, dönüştürme sonucunu depolamak için kullanılan sabit boyutlu statik arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf **malloc**kullanarak belleği ayırır ve nesne kapsam dışına çıktığında belleği serbest eder. Bu, ATL'nin önceki sürümlerinde bulunan metin dönüştürme makrolarının aksine, bu sınıfın döngülerde kullanımının güvenli olmasını ve yığını nakışlamamasını sağlar.

Sınıf yığınüzerinde bellek ayırmaya çalışır ve başarısız olursa, `AtlThrow` E_OUTOFMEMORY bir argüman ile çağırır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, kod sayfasını sınıfın oluşturucusuna ikinci parametre olarak belirtin.

Aşağıdaki makrolar bu sınıfa dayanır:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Aşağıdaki typedef bu sınıfa dayanır:

- CW2A

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="cw2aexcw2aex"></a><a name="cw2aex"></a>CW2AEX::CW2AEX

Oluşturucu.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Dönüştürme gerçekleştirmek için kullanılan kod sayfası. Daha fazla bilgi için Windows SDK fonksiyonu [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) için kod sayfası parametre tartışmasına bakın.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="cw2aexcw2aex"></a><a name="dtor"></a>CW2AEX::~CW2AEX

Yıkıcı.

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="cw2aexm_psz"></a><a name="m_psz"></a>CW2AEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPSTR m_psz;
```

## <a name="cw2aexm_szbuffer"></a><a name="m_szbuffer"></a>CW2AEX::m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
char m_szBuffer[t_nBufferLength];
```

## <a name="cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CW2AEX::operatör LPSTR

Dönüşüm işleci.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
