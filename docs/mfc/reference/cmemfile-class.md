---
title: CMemFile sınıfı
description: CMemFile sınıfında kullanılabilir olan ve bellek dosyalarıyla çalışmanıza olanak sağlayan işlevleri açıklar.
ms.date: 07/23/2020
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CmemFile::GetBufferPtr
- AFX/CMemFile::GrowFile"
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GetBufferPtr
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: edd1d8b8d3979427602bdb61fc7647aec15d58b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222946"
---
# <a name="cmemfile-class"></a>CMemFile sınıfı

Bellek dosyalarını destekleyen [CFile](../../mfc/reference/cfile-class.md)ile türetilmiş sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMemFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMemFile:: CMemFile](#cmemfile)|Bir bellek dosyası nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMemFile:: Attach](#attach)|Bir bellek bloğunu öğesine ekler `CMemFile` .|
|[CMemFile::D etach](#detach)|Bellek bloğunu ' dan ayırır `CMemFile` ve bellek bloğuna ayrılan bir işaretçi döndürür.|
|[CMemFile:: GetBufferPtr](#getbufferptr)|Bellek dosyasını yedekleyen bellek arabelleğini alma veya yazma.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMemFile:: ayırma](#alloc)|Bellek ayırma davranışını değiştirmek için geçersiz kılın.|
|[CMemFile:: ücretsiz](#free)|Belleği kaldırma davranışını değiştirmek için geçersiz kılın.|
|[CMemFile:: GrowFile](#growfile)|Bir dosya büyümekte olan davranışı değiştirmek için geçersiz kılar.|
|[CMemFile:: Memckopyala](#memcpy)|Dosya okurken ve yazarken bellek kopyalama davranışını değiştirmek için geçersiz kılın.|
|[CMemFile:: realloc](#realloc)|Belleği yeniden ayırma davranışını değiştirmek için geçersiz kılın.|

## <a name="remarks"></a>Açıklamalar

Bu bellek dosyaları, dosyanın disk yerine RAM 'te depolanmasının dışında disk dosyaları gibi davranır. İçin bir bellek dosyası yararlıdır:

- hızlı geçici depolama
- bağımsız süreçler arasında ham baytları aktarma
- bağımsız süreçler arasında seri hale getirilmiş nesneleri aktarma

`CMemFile`nesneler, kendi belleğini otomatik olarak ayırabilir. Ya da, Attach 'i çağırarak, nesnesine kendi bellek bloğunu ekleyebilirsiniz `CMemFile` . [Attach](#attach) Her iki durumda da, sıfır değilse bellek dosyası otomatik olarak büyümeye yönelik bellek, `nGrowBytes` boyutlandırılmış artışlarla ayrılır `nGrowBytes` .

Bellek bloğu, `CMemFile` bellek ilk olarak nesne tarafından ayrıldıysa nesne yok edilirken otomatik olarak silinir `CMemFile` ; Aksi takdirde, nesnesine eklediğiniz belleği ayırmayı kaldırma sorumluluğunuz olur.

Ayırma yöntemini çağırarak, nesneyi nesneden ayırdığınızda sağlanan işaretçi aracılığıyla bellek bloğuna erişebilirsiniz `CMemFile` . [Detach](#detach)

En yaygın kullanımı, `CMemFile` bir `CMemFile` nesnesi oluşturmak ve [CFile](../../mfc/reference/cfile-class.md) üye işlevlerini çağırarak kullanmaktır. `CMemFile`Otomatik olarak bir açılır. oluşturma: yalnızca disk dosyaları için kullanılan [CFile:: Open](../../mfc/reference/cfile-class.md#open)öğesini çağırmazsınız. `CMemFile`Bir disk dosyası kullandığından, veri üyesi `CFile::m_hFile` kullanılmıyor.

`CFile` [Yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange)ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) üye işlevleri için uygulanmaz `CMemFile` . Bu işlevleri bir nesne üzerinde çağırırsanız `CMemFile` , bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)alırsınız.

`CMemFile`bellek ayırmak, yeniden ayırmak ve serbest bırakmak için [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md)ve [Free](../../c-runtime-library/reference/free.md) çalışma zamanı kitaplığı işlevlerini kullanır; ve okuma ve yazma sırasında belleği kopyalamaya engel olan iç [memca](../../c-runtime-library/reference/memcpy-wmemcpy.md) . Bu davranışı veya `CMemFile` bir dosyayı büyürken davranışını değiştirmek isterseniz, kendi sınıfınızı ' dan türetirsiniz `CMemFile` ve uygun işlevleri geçersiz kılın.

Hakkında daha fazla bilgi için `CMemFile` MFC ve [bellek yönetimi 'NDEKI (MFC)](../../mfc/memory-management.md) makaleler [dosyalarına](../../mfc/files-in-mfc.md) bakın ve *çalışma zamanı kitaplığı başvurusunda* [Dosya işleme](../../c-runtime-library/file-handling.md) ' ya bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile:: ayırma

Bu işlev `CMemFile` üye işlevleri tarafından çağırılır.

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Ayrılacak bellek bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğunun işaretçisi veya ayırma başarısız olduysa NULL.

### <a name="remarks"></a>Açıklamalar

Özel bellek ayırmayı uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsınız, muhtemelen [ücretsiz](#free) ve [realloc](#realloc) 'i de geçersiz kılmak isteyeceksiniz.

Varsayılan uygulama, bellek ayırmak için bir çalışma zamanı kitaplığı işlevi [malloc](../../c-runtime-library/reference/malloc.md) kullanır.

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile:: Attach

Bir bellek bloğunu öğesine eklemek için bu işlevi çağırın `CMemFile` .

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuffer*<br/>
İliştirilebilecek arabelleğin işaretçisi `CMemFile` .

*nBufferSize*<br/>
Arabellek boyutunu bayt cinsinden belirten bir tamsayı.

*nGrowBytes*<br/>
Bayt cinsinden bellek ayırma artışı.

### <a name="remarks"></a>Açıklamalar

Bu, bellek `CMemFile` dosyası olarak bellek bloğunu kullanılmasına neden olur.

*NGrowBytes* 0 ise, `CMemFile` Dosya uzunluğu *nBufferSize*olarak ayarlanır. Bu, bellek bloğundaki verilerin iliştirilme öncesinde `CMemFile` dosya olarak kullanılacağı anlamına gelir. Bu şekilde oluşturulan bellek dosyaları büyütümdü.

Dosya `CMemFile` büyütülemediğinden, dosyayı büyütmeyi denememeye dikkat edin. Örneğin, `CMemFile` [CFile](../../mfc/reference/cfile-class.md#write) 'ın geçersiz kılmalarını çağırmayın: sonuna yazmak Için yazma veya [CFile: SetLength](../../mfc/reference/cfile-class.md#setlength) değerini *nBufferSize*'dan daha uzun bir uzunluğa çağırma.

*NGrowBytes* 0 ' dan büyükse, eklediğiniz `CMemFile` bellek bloğunun içeriğini yoksayar. Geçersiz kılmayı kullanarak bellek dosyasının içeriğini sıfırdan yazmanız gerekir `CMemFile` `CFile::Write` . Dosyanın sonunu geçti veya geçersiz kılmayı çağırarak dosyayı Büyüyorsam `CMemFile` `CFile::SetLength` , `CMemFile` *nGrowBytes*artışlarla bellek ayırmayı büyüyerek büyütür. Bellek ayırmayı büyütmek için geçirdiğiniz bellek bloğu, `Attach` [ayırma](#alloc)ile uyumlu bir yöntemle ayrılmamışsa başarısız olur. Varsayılan uygulamasıyla uyumlu olmak için `Alloc` bellek, [malloc](../../c-runtime-library/reference/malloc.md) veya [calloc](../../c-runtime-library/reference/calloc.md)çalışma zamanı kitaplık işleviyle ayırmanız gerekir.

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile:: CMemFile

İlk aşırı yükleme boş bir bellek dosyası açar.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parametreler

*nGrowBytes*<br/>
Bayt cinsinden bellek ayırma artışı.

*lpBuffer* *NBufferSize*boyutunun bilgilerini alan bir arabelleğin işaretçisi.

*nBufferSize*<br/>
Dosya arabelleğinin bayt cinsinden boyutunu belirten bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Dosya Oluşturucu tarafından açılır. [CFile:: Open](../../mfc/reference/cfile-class.md#open)çağrısı yapmayın.

İkinci aşırı yükleme, ilk oluşturucuyu kullandıysanız ve hemen aynı parametrelerle [Attach](#attach) olarak adlandırılan ile aynı şekilde davranır. Ayrıntılar için bkz. `Attach`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::D etach

Tarafından kullanılan bellek bloğuna yönelik bir işaretçi almak için bu işlevi çağırın `CMemFile` .

```
BYTE* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek dosyasının içeriğini içeren bellek bloğunun işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak, ' i de kapatır `CMemFile` . `CMemFile` [Bağlama](#attach)çağrısı yaparak bellek bloğunu öğesine yeniden iliştirebilirsiniz. Dosyayı yeniden iliştirmek ve içindeki verileri kullanmak istiyorsanız, çağrılmadan önce dosyanın uzunluğunu almak için [CFile:: GetLength](../../mfc/reference/cfile-class.md#getlength) çağrısı yapmanız gerekir `Detach` . ' A bir bellek bloğu eklerseniz `CMemFile` , verilerini ( `nGrowBytes` = = 0) kullanabilmeniz için bellek dosyası büyütüyemiyoruz.

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile:: ücretsiz

Bu işlev `CMemFile` üye işlevleri tarafından çağırılır.

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>Parametreler

*lpMem*<br/>
Serbest bırakmak için bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Özel bellek ayırmayı kaldırma uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsınız, büyük olasılıkla [ayırma](#alloc) ve [realloc](#realloc) 'i de geçersiz kılmak isteyeceksiniz.

## <a name="cmemfilegetbufferptr"></a><a name="getbufferptr"></a>CMemFile:: GetBufferPtr

Bellek dosyasını yedekleyen bellek arabelleğini alma veya yazma.

```cpp
virtual UINT GetBufferPtr(
    UINT nCommand,
    UINT nCount = 0,
    void** ppBufStart = NULL,
    void** ppBufMax = NULL
);
```

### <a name="parameters"></a>Parametreler

*Nyürütülen komut*<br/>
Gerçekleştirilecek [buffercommand](buffercommand-enumeration.md) ( `bufferCheck` , `bufferCommit` , `bufferRead` veya `bufferWrite` ).

*nCount*<br/>
*NCommand*öğesine bağlı olarak, arabellekteki, yazılacak veya yürütülecek Arabellekteki bayt sayısı. Arabellekten okurken, geçerli konumdan dosyanın sonuna bir arabellek döndürmek için-1 belirtin.

*ppBufStart*<br/>
dışı Arabelleğin başlangıcı. `NULL` *NCommand* olduğunda olmalıdır `bufferCommit` .

*ppBufMax*<br/>
dışı Arabelleğin sonu. `NULL`NCommand olduğunda olmalıdır `bufferCommit` .

### <a name="return-value"></a>Dönüş Değeri

| *komut* değeri | Döndürülen değer |
|--|--|
| `buffercheck` | Doğrudan arabelleğe alma destekleniyorsa, yoksa, [Bufferdirect](buffercommand-enumeration.md) döndürür. |
| `bufferCommit` | Döndürdüğü`0` |
| `bufferRead` veya `bufferWrite` | Döndürülen arabellek alanındaki bayt sayısını döndürür. *Ppbufstart* ve *Ppbufmax* , okuma/yazma arabelleğinin başlangıcını ve sonuna işaret edin.  |

### <a name="remarks"></a>Açıklamalar

Bellek arabelleğindeki () geçerli konum, `m_nPosition` *nkomuta*bağlı olarak aşağıdaki yollarla gelişmiş bir şekilde yapılır:

| *Nyürütülen komut* | arabellek konumu |
|-|-|
| `bufferCommit` | Geçerli konum, kaydedilmiş arabelleğin boyutuna göre ilerletir. |
| `bufferRead` | Geçerli konum, okuma arabelleğinin boyutuna göre ilerletir. |

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile:: GrowFile

Bu işlev, üye işlevlerinin birkaçı tarafından çağırılır `CMemFile` .

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>Parametreler

*dwNewLen*<br/>
Bellek dosyasının yeni boyutu.

### <a name="remarks"></a>Açıklamalar

Dosya boyutunu büyüyerek değiştirmek istiyorsanız, geçersiz kılabilirsiniz `CMemFile` . Varsayılan uygulama, var olan bir bloğu büyütmek [(veya bir](#alloc) bellek bloğu oluşturmak için ayırmak) Için [realloc](#realloc) çağırır; bu da, `nGrowBytes` Oluşturucu veya [iliştirme](#attach) çağrısında belirtilen değerin katları halinde bellek ayırır.

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile:: Memckopyala

Bu işlev, `CMemFile` bellek dosyasına ve veri aktarmak Için [CFile:: Read](../../mfc/reference/cfile-class.md#read) ve [CFile:: Write](../../mfc/reference/cfile-class.md#write) geçersiz kılmaları tarafından çağrılır.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*lpMemTarget*<br/>
Kaynak belleğin kopyalanacağı bellek bloğunun işaretçisi.

*lpMemSource*<br/>
Kaynak bellek bloğunun işaretçisi.

*nBytes*<br/>
Kopyalanacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*Lpmemtarget*kopyası.

### <a name="remarks"></a>Açıklamalar

Bu bellek kopyalarının yolunu değiştirmek istiyorsanız bu işlevi geçersiz kılın `CMemFile` .

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile:: realloc

Bu işlev `CMemFile` üye işlevleri tarafından çağırılır.

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*lpMem*<br/>
Yeniden ayrılacak bellek bloğunun işaretçisi.

*nBytes*<br/>
Bellek bloğunun yeni boyutu.

### <a name="return-value"></a>Dönüş Değeri

Yeniden ayırma başarısız olursa bellek bloğunun bir işaretçisi (ve muhtemelen taşınmış olabilir) veya NULL.

### <a name="remarks"></a>Açıklamalar

Özel bellek yeniden ayırma uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsınız, büyük olasılıkla [ayırma](#alloc) ve [serbest bırakma](#free) işlevlerini de geçersiz kılmak isteyeceksiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
