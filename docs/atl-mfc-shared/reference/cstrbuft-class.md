---
description: 'Daha fazla bilgi edinin: CStrBufT sınıfı'
title: CStrBufT sınıfı
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
ms.openlocfilehash: 4cc38f13d740b7def65c6f958d53af7b367adcb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166622"
---
# <a name="cstrbuft-class"></a>CStrBufT sınıfı

Bu sınıf, için otomatik kaynak Temizleme `GetBuffer` ve `ReleaseBuffer` var olan bir nesne üzerinde çağrılar sağlar `CStringT` .

## <a name="syntax"></a>Sözdizimi

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Parametreler

*TCharType*<br/>
Sınıfın karakter türü `CStrBufT` . Aşağıdakilerden biri olabilir:

- **`char`** (ANSI karakter dizeleri için)

- **`wchar_t`** (Unicode karakter dizeleri için)

- TCHAR (hem ANSI hem de Unicode karakter dizeleri için)

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|PCXSTR|Sabit dize işaretçisi.|
|PXSTR|Dize işaretçisi.|
|`StringType`|Arabelleğini Bu sınıf şablonunun özelleştirilmesi tarafından değiştirilecek olan dize türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT:: CStrBufT](#cstrbuft)|Dize arabelleği nesnesi için Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT:: SetLength](#setlength)|İlişkili dize nesnesinin karakter arabelleği uzunluğunu ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT:: operator PCXSTR](#operator_pcxstr)|**`const`** İlişkili dize nesnesinin karakter arabelleğine yönelik bir işaretçi alır.|
|[CStrBufT:: operator PXSTR](#operator_pxstr)|İlişkili dize nesnesinin karakter arabelleğine yönelik bir işaretçi alır.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT:: AUTO_LENGTH](#auto_length)|Yayındaki dizenin yeni uzunluğunu otomatik olarak belirleme.|
|[CStrBufT:: SET_LENGTH](#set_length)|GetBuffer sırasında dize nesnesinin uzunluğunu ayarla|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, çağrıları [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)ya da [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) ve ile değiştirmek için sarmalayıcı sınıfı olarak kullanılır `ReleaseBuffer` .

Öncelikli olarak bir yardımcı sınıf olarak tasarlanan, `CStrBufT` geliştiricilerin nasıl veya ne zaman çağrılacağını endişelenmeden bir dize nesnesinin karakter arabelleğine çalışması için kolay bir yol sağlar `ReleaseBuffer` . Bu mümkündür çünkü sarmalayıcı nesne bir özel durum veya birden çok çıkış kodu yolundan doğal olarak kapsam dışına çıkar; yıkıcının dize kaynağını serbest bırakma olmasına neden olur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a> CStrBufT:: AUTO_LENGTH

Yayındaki dizenin yeni uzunluğunu otomatik olarak belirleme.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Açıklamalar

Yayındaki dizenin yeni uzunluğunu otomatik olarak belirleme. Dize null ile sonlandırılmış olmalıdır.

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a> CStrBufT:: CStrBufT

Bir buffer nesnesi oluşturur.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Arabellek ile ilişkilendirilen dize nesnesi. Genellikle, geliştirici önceden tanımlanmış tür tanımları `CStrBuf` (TCHAR Variant), `CStrBufA` ( **`char`** Varyant) ve `CStrBufW` ( **`wchar_t`** Varyant) kullanır.

*nMinLength*<br/>
Karakter arabelleğinin en küçük uzunluğu.

*dwFlags*<br/>
Dize uzunluğunun otomatik olarak belirlendiğini belirler. Aşağıdakilerden biri olabilir:

- AUTO_LENGTH dize uzunluğu, [CSimpleStringT:: Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) çağrıldığında otomatik olarak belirlenir. Dize null ile sonlandırılmış olmalıdır. Varsayılan değer.

- [CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) çağrıldığında SET_LENGTH dize uzunluğu ayarlanır.

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesi için bir dize arabelleği oluşturur. Oluşturma sırasında [CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) veya [CSimpleStringT:: GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) çağrılır.

Kopya oluşturucusunun olduğunu unutmayın **`private`** .

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a> CStrBufT:: operator PCXSTR

İlişkili dize nesnesinde depolanan karakterlere doğrudan C stili dize olarak erişir.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir dize nesnesinin karakter arabelleğine bir işaretçi döndürmek için bu işlevi çağırın. Dize nesnesinin içeriği bu işaretçiyle değiştirilemez.

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a> CStrBufT:: operator PXSTR

İlişkili dize nesnesinde depolanan karakterlere doğrudan C stili dize olarak erişir.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin verilerine yönelik bir karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir dize nesnesinin karakter arabelleğine bir işaretçi döndürmek için bu işlevi çağırın. Geliştirici dize nesnesinin içeriğini bu işaretçiyle değiştirebilir.

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a> CStrBufT::P CXSTR

Sabit dize işaretçisi.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a> CStrBufT::P XSTR

Dize işaretçisi.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a> CStrBufT:: SET_LENGTH

Dize nesnesinin uzunluğunu `GetBuffer` zamanında ayarlayın.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Açıklamalar

GetBuffer sırasında dize nesnesinin uzunluğunu ayarlayın.

Dize arabelleği nesnesi oluşturulduğunda [CSimpleStringT:: GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT:: GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) çağrılıp çağrılamayacağını belirler.

## <a name="cstrbuftsetlength"></a><a name="setlength"></a> CStrBufT:: SetLength

Karakter arabelleğinin uzunluğunu ayarlar.

```cpp
void SetLength(int nLength);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
Dize nesnesinin karakter arabelleğinin yeni uzunluğu.

> [!NOTE]
> Oluşturucusunun içinde belirtilen en düşük arabellek uzunluğuna eşit veya ondan küçük olmalıdır `CStrBufT` .

### <a name="remarks"></a>Açıklamalar

Buffer nesnesiyle temsil edilen dizenin uzunluğunu ayarlamak için bu işlevi çağırın.

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a> CStrBufT:: StringType

Arabelleğini Bu sınıf şablonunun özelleştirilmesi tarafından değiştirilecek olan dize türü.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Açıklamalar

`TCharType` , sınıf şablonunu özelleştirmek için kullanılan karakter türüdür.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
