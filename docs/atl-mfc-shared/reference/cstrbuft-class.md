---
title: CStrBufT Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 84c67aa8ea819f420368a72a2374f800f3d89055
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317641"
---
# <a name="cstrbuft-class"></a>CStrBufT Sınıfı

Bu sınıf için `GetBuffer` otomatik kaynak `ReleaseBuffer` temizleme sağlar `CStringT` ve varolan bir nesneyi çağırır.

## <a name="syntax"></a>Sözdizimi

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Parametreler

*TCharType*<br/>
`CStrBufT` Sınıfın karakter türü. Aşağıdakilerden biri olabilir:

- **char** (ANSI karakter dizeleri için)

- **wchar_t** (Unicode karakter dizeleri için)

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için)

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|PCXSTR|Sabit bir dize için bir işaretçi.|
|PXSTR|Dize için bir işaretçi.|
|`StringType`|Arabelleği bu sınıf şablonunun uzmanlıkları tarafından manipüle edilecek dize türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|Dize arabellek nesnesinin oluşturucusu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|İlişkili dize nesnesinin karakter arabellek uzunluğunu ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CStrBufT::operatör PCXSTR](#operator_pcxstr)|İlişkili dize nesnesinin karakter arabelleği için bir **const** işaretçisi alır.|
|[CStrBufT::operatör PXSTR](#operator_pxstr)|İlişkili dize nesnesinin karakter arabelleği için bir işaretçi alır.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|Yayımdaki dizenin yeni uzunluğunu otomatik olarak belirleyin.|
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer zamanında dize nesnesinin uzunluğunu ayarlama|

## <a name="remarks"></a>Açıklamalar

Bu sınıf [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)veya [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) ve `ReleaseBuffer`aramaları değiştirmek için bir sarmalayıcı sınıfı olarak kullanılır.

Öncelikle yardımcı sınıf olarak `CStrBufT` tasarlanmış, bir geliştirici için uygun bir yol nasıl ve ne zaman aramak `ReleaseBuffer`için endişelenmeden bir dize nesnenin karakter arabelleği ile çalışmak için sağlar. Bu, sarıcı nesnesi bir özel durum veya birden çok çıkan kod yolu durumunda doğal olarak kapsam dışına gittiğinden mümkündür; destructor dize kaynağı serbest neden.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr.h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH

Yayımdaki dizenin yeni uzunluğunu otomatik olarak belirleyin.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Açıklamalar

Yayımdaki dizenin yeni uzunluğunu otomatik olarak belirleyin. Dize geçersiz kılınmalıdır.

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT::CStrBufT

Bir arabellek nesnesi oluşturuyor.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Arabellek ile ilişkili dize nesnesi. Tipik olarak, geliştirici `CStrBuf` önceden tanımlanmış typedefs (TCHAR `CStrBufA` varyant),**(char** varyantı) ve `CStrBufW` **(wchar_t** varyantı) kullanır.

*nMinLength*<br/>
Karakter arabelleği minimum uzunluğu.

*Dwflags*<br/>
Dize uzunluğunun otomatik olarak belirlenip belirlenmediğini belirler. Aşağıdakilerden biri olabilir:

- AUTO_LENGTH String uzunluğu [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) çağrıldığında otomatik olarak belirlenir. Dize geçersiz kılınmalıdır. Varsayılan değer.

- [cSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) çağrıldığında SET_LENGTH String uzunluğu ayarlanır.

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesi için bir dize arabelleği oluşturur. İnşaat sırasında [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) veya [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) denir.

Kopya oluşturucunun **özel**olduğunu unutmayın.

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT::operatör PCXSTR

İlişkili dize nesnesinde depolanan karakterlere C stili dize olarak doğrudan erişir.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dize verilerine bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir dize nesnesinin karakter arabelleği için bir işaretçi dönmek için bu işlevi arayın. Dize nesnesinin içeriği bu işaretçiyle değiştirilemez.

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT::operatör PXSTR

İlişkili dize nesnesinde depolanan karakterlere C stili dize olarak doğrudan erişir.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dize verilerine bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir dize nesnesinin karakter arabelleği için bir işaretçi dönmek için bu işlevi arayın. Geliştirici bu işaretçi ile dize nesnesinin içeriğini değiştirebilir.

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR

Sabit bir dize için bir işaretçi.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::PXSTR

Dize için bir işaretçi.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>CStrBufT::SET_LENGTH

Dize nesnesinin uzunluğunu `GetBuffer` zaman anına ayarlayın.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Açıklamalar

GetBuffer zamanında dize nesnesinin uzunluğunu ayarlayın.

[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) dize arabellek nesnesi oluşturulduğunda çağrılır belirler.

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT::SetLength

Karakter arabelleği uzunluğunu ayarlar.

```
void SetLength(int nLength);
```

### <a name="parameters"></a>Parametreler

*nUzunluk*<br/>
Dize nesnesinin karakter arabelleği yeni uzunluğu.

> [!NOTE]
> `CStrBufT`'nin yapısında belirtilen minimum arabellek uzunluğundan daha az veya eşit olmalıdır.

### <a name="remarks"></a>Açıklamalar

Arabellek nesnesi tarafından temsil edilen dize uzunluğunu ayarlamak için bu işlevi çağırın.

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT::StringType

Arabelleği bu sınıf şablonunun uzmanlıkları tarafından manipüle edilecek dize türü.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Açıklamalar

`TCharType`sınıf şablonu uzmanlaşmak için kullanılan karakter türüdür.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
