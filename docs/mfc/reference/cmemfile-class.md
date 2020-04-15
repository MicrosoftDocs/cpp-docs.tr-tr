---
title: CMemFile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: 46937795499fd9f697f9778c263a1ee011777c0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370017"
---
# <a name="cmemfile-class"></a>CMemFile Sınıfı

Bellek dosyalarını destekleyen [CFile](../../mfc/reference/cfile-class.md)türetilmiş sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMemFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMemFile::CMemFile](#cmemfile)|Bir bellek dosyası nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMemFile::Ekle](#attach)|Bir bellek bloğunu `CMemFile`.|
|[CMemFile::Detach](#detach)|Bellek bloğunu ayırır `CMemFile` ve ayrılan bellek bloğuna bir işaretçiyi döndürür.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMemFile::Alloc](#alloc)|Bellek ayırma davranışını değiştirmek için geçersiz kılma.|
|[CMemFile::Ücretsiz](#free)|Bellek deallocation davranışını değiştirmek için geçersiz kılma.|
|[CMemFile::GrowFile](#growfile)|Dosya yıklarken davranışı değiştirmek için geçersiz kılın.|
|[CMemFile::Memcpy](#memcpy)|Dosyaları okurken ve yazarken bellek kopyalama davranışını değiştirmek için geçersiz kılın.|
|[CMemFile::Realloc](#realloc)|Bellek yeniden ayırma davranışını değiştirmek için geçersiz kılma.|

## <a name="remarks"></a>Açıklamalar

Bu bellek dosyaları, dosyanın diskte değil DE RAM'de depolanmış olması dışında disk dosyaları gibi olur. Bellek dosyası, hızlı geçici depolama veya ham baytveya seri leştirilmiş nesnelerin bağımsız işlemler arasında aktarılması için yararlıdır.

`CMemFile`nesneler otomatik olarak kendi bellek lerini tahsis edebilir veya `CMemFile` [ekle'yi](#attach)arayarak kendi bellek bloğunuzu nesneye ekleyebilirsiniz. Her iki durumda da, bellek dosyasını otomatik `nGrowBytes`olarak büyütmek için `nGrowBytes` bellek sıfır değilse boyutlandırılmış artışlarla ayrılır.

Bellek ilk olarak `CMemFile` `CMemFile` nesne tarafından ayrılmışsa, bellek bloğu nesnenin yok edilmesinden sonra otomatik olarak silinir; aksi takdirde, nesneye iliştirdiğiniz belleği ayırmaksizin sorumlu olursunuz.

Ayır'ı arayarak `CMemFile` nesneden ayırdığınızda verilen işaretçi aracılığıyla bellek [bloğuna](#detach)erişebilirsiniz.

En yaygın kullanımı `CMemFile` bir `CMemFile` nesne oluşturmak ve [CFile](../../mfc/reference/cfile-class.md) üye işlevleri çağırarak kullanmaktır. Otomatik olarak `CMemFile` açılan bir şey oluşturmanın: CFile'ı aramadığınızı [unutmayın::Aç](../../mfc/reference/cfile-class.md#open), yalnızca disk dosyaları için kullanılır. Disk `CMemFile` dosyası kullanmadığından, veri üyesi `CFile::m_hFile` kullanılmaz.

Üye `CFile` işlevleri [Yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) için `CMemFile`uygulanmaz . Bu işlevleri bir `CMemFile` nesne üzerinde çağırırsanız, [cnotsupportedException](../../mfc/reference/cnotsupportedexception-class.md)alırsınız.

`CMemFile`bellek ayırmak, yeniden tahsis etmek ve anlaşma sağlamak için çalışma zamanı kitaplık işlevleri [malloc,](../../c-runtime-library/reference/malloc.md) [realloc](../../c-runtime-library/reference/realloc.md)ve [ücretsiz](../../c-runtime-library/reference/free.md) kullanır; ve içsel [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) okurken ve yazarken kopya bellek engellemek için. Bir dosya büyürken `CMemFile` bu davranışı veya davranışı değiştirmek istiyorsanız, kendi sınıfınızı türetin `CMemFile` ve uygun işlevleri geçersiz kılın.

Hakkında daha `CMemFile`fazla bilgi için, MFC ve [Bellek Yönetimi (MFC)](../../mfc/memory-management.md) makale [dosyaları](../../mfc/files-in-mfc.md) ve *Run-Time Kitaplığı Başvurusu* [Dosya İşleme](../../c-runtime-library/file-handling.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile::Alloc

Bu işlev üye `CMemFile` işlevler tarafından çağrılır.

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Ayrılacak bellek baytlarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğuna işaretçi veya ayırma başarısız olursa NULL.

### <a name="remarks"></a>Açıklamalar

Özel bellek ayırma uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsanız, büyük olasılıkla [Free](#free) ve [Realloc'u](#realloc) da geçersiz kılmak istersiniz.

Varsayılan uygulama bellek ayırmak için çalışma zamanı kitaplık işlevini [malloc](../../c-runtime-library/reference/malloc.md) kullanır.

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile::Ekle

Bir bellek bloğu eklemek için `CMemFile`bu işlevi çağırın.

```
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parametreler

*lpBuffer*<br/>
Eklenecek arabellek `CMemFile`işaretçisi.

*nBufferSize*<br/>
Arabellek baytboyutunu belirten bir araseme.

*nGrowBytes*<br/>
Baytlarda bellek ayırma artış.

### <a name="remarks"></a>Açıklamalar

Bu, `CMemFile` bellek dosyası olarak bellek bloğunu kullanmaya neden olur.

*nGrowBytes* 0 ise, `CMemFile` dosya uzunluğunu *nBufferSize*olarak ayarlar. Bu, eklenmeden `CMemFile` önce bellek bloğundaki verilerin dosya olarak kullanılacağı anlamına gelir. Bu şekilde oluşturulan bellek dosyaları büyütülemez.

Dosya büyütülemediğinden, dosyayı `CMemFile` büyütmeye çalışmamaya dikkat edin. Örneğin, [CFile'ın](../../mfc/reference/cfile-class.md#write) `CMemFile` geçersiz kılmalarını aramayın:Sonuna kadar yazmak için yazın veya [CFile:SetLength'ı](../../mfc/reference/cfile-class.md#setlength) *nBufferSize'dan*daha uzun bir uzunluğa sahip olarak aramayın.

*nGrowBytes* 0'dan büyükse, `CMemFile` iliştirdiğiniz bellek bloğunun içeriğini yok sayar. Bellek dosyasının içeriğini geçersiz kılmayı `CMemFile` kullanarak sıfırdan yazmanız `CFile::Write`gerekir. Dosyanın sonuna yazmayı veya geçersiz `CMemFile` kılmayı arayarak dosyayı büyütmeye `CFile::SetLength`çalışırsanız, `CMemFile` bellek ayırmasını *nGrowBytes'in*artışlarında büyütecektir. Geçtiğiniz bellek bloğu [Alloc](#alloc)ile uyumlu `Attach` bir yöntemle tahsis edilmediyse bellek ayırmayı büyütmek başarısız olur. Varsayılan uygulama ile uyumlu `Alloc`olması için, çalışma zamanı kitaplık işlevi [malloc](../../c-runtime-library/reference/malloc.md) veya [calloc](../../c-runtime-library/reference/calloc.md)ile bellek ayırmak gerekir.

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile::CMemFile

İlk aşırı yükleme boş bir bellek dosyasını açar.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parametreler

*nGrowBytes*<br/>
Baytlarda bellek ayırma artış.

*lpBuffe*r İşaretçi boyutu *nBufferSize*bilgi alan bir arabellek için .

*nBufferSize*<br/>
Dosya arabelleği boyutunu baytolarak belirten bir arasayı.

### <a name="remarks"></a>Açıklamalar

Dosyanın oluşturucu tarafından açıldığını ve CFile'ı aramamanız gerektiğini [unutmayın::Aç.](../../mfc/reference/cfile-class.md#open)

İkinci aşırı yük, ilk oluşturucuyu kullanmış ve hemen aynı parametrelerle [Ekle](#attach) olarak adlandırılan gibi davranır. Ayrıntılar için bkz. `Attach`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::Detach

Tarafından kullanılan bellek bloğuna işaretçi almak `CMemFile`için bu işlevi arayın.

```
BYTE* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek dosyasının içeriğini içeren bellek bloğuna işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi çağırmak da `CMemFile`kapatır. [Ekle'yi](#attach)arayarak bellek `CMemFile` bloğunu yeniden ekleyebilirsiniz. Dosyayı yeniden takmak ve dosyadaki verileri kullanmak istiyorsanız, çağırmadan `Detach`önce dosyanın uzunluğunu almak için [CFile::GetLength'ı](../../mfc/reference/cfile-class.md#getlength) aramalısınız. Verilerini kullanabilmek `CMemFile` `nGrowBytes` için bir bellek bloğu (== 0) bağlarsanız, bellek dosyasını büyütemezsiniz.

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile::Ücretsiz

Bu işlev üye `CMemFile` işlevler tarafından çağrılır.

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>Parametreler

*lpMem*<br/>
Belleğin ayrılması için işaretçi.

### <a name="remarks"></a>Açıklamalar

Özel bellek deallocation uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsanız, muhtemelen [Alloc](#alloc) ve [Realloc'u](#realloc) da geçersiz kılmak istersiniz.

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile::GrowFile

Bu işlev, üye işlevlerin birkaçı `CMemFile` tarafından çağrılır.

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>Parametreler

*dwNewLen*<br/>
Bellek dosyasının yeni boyutu.

### <a name="remarks"></a>Açıklamalar

Dosyanın nasıl `CMemFile` büyüdüğünü değiştirmek istiyorsanız geçersiz kılınabilirsiniz. Varsayılan uygulama, [Realloc'u](#realloc) varolan bir bloğu (veya bellek bloğu oluşturmak için [Alloc)](#alloc) büyütmeye çağırır ve bellek oluşturucu veya `nGrowBytes` [Ekle](#attach) çağrısında belirtilen değerin katları arasında ayırır.

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile::Memcpy

Bu işlev CFile `CMemFile` geçersiz kılmaları tarafından çağrılır::Oku ve [CFile::Bellek](../../mfc/reference/cfile-class.md#write) dosyasına ve bellekten veri aktarmak için yazın. [CFile::Read](../../mfc/reference/cfile-class.md#read)

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*lpMemTarget*<br/>
Kaynak belleğin kopyalanacağı bellek bloğunu işaretçi.

*lpMemKaynak*<br/>
Kaynak bellek bloğuna işaretçi.

*nBayt*<br/>
Kopyalanacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*lpMemTarget*bir kopyası .

### <a name="remarks"></a>Açıklamalar

Bu bellek kopyalarını `CMemFile` yapan şekilde değiştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile::Realloc

Bu işlev üye `CMemFile` işlevler tarafından çağrılır.

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parametreler

*lpMem*<br/>
Yeniden tahsis edilecek bellek bloğuna işaretçi.

*nBayt*<br/>
Bellek bloğu için yeni boyut.

### <a name="return-value"></a>Dönüş Değeri

Yeniden ayrılan (ve büyük olasılıkla taşınan) bellek bloğuna işaretçi veya yeniden ayırma başarısız olduysa NULL.

### <a name="remarks"></a>Açıklamalar

Özel bellek yeniden ayırma uygulamak için bu işlevi geçersiz kılın. Bu işlevi geçersiz kılarsanız, büyük olasılıkla [Alloc](#alloc) ve [Free'yi](#free) de geçersiz kılmak istersiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
