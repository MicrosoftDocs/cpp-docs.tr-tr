---
title: CSharedFile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: e6a713ac9d9e906ec204d4a52b43ed51c08fd99c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318427"
---
# <a name="csharedfile-class"></a>CSharedFile Sınıfı

Paylaşılan bellek dosyalarını destekleyen [CMemFile](../../mfc/reference/cmemfile-class.md)türetilmiş sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|Bir `CSharedFile` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|Paylaşılan bellek dosyasını kapatır ve bellek bloğunun tutamacını döndürür.|
|[CSharedFile::SetHandle](#sethandle)|Paylaşılan bellek dosyasını bellek bloğuna bağlar.|

## <a name="remarks"></a>Açıklamalar

Bellek dosyaları disk dosyaları gibi olur. Fark, bir bellek dosyası disk yerine RAM saklanır. Bellek dosyası, hızlı geçici depolama veya ham bayt veya seri leştirilmiş nesneleri bağımsız işlemler arasında aktarmak için yararlıdır.

Paylaşılan bellek dosyaları, [globalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows işlevi ile ayrılan bellekteki diğer bellek dosyalarından farklıdır. Sınıf `CSharedFile` verileri genel olarak ayrılmış bir bellek bloğunda (kullanılarak `GlobalAlloc`oluşturulmuş) depolar ve bu bellek bloğu DDE, Pano veya diğer OLE/COM tek düzen veri aktarım işlemleri kullanılarak paylaşılabilir, `IDataObject`örneğin.

`GlobalAlloc`malloc tarafından döndürülen işaretçi gibi bellek için bir [malloc](../../c-runtime-library/reference/malloc.md)işaretçi yerine bir HGLOBAL tutamacı döndürür. HGLOBAL kolu belirli uygulamalarda gereklidir. Örneğin, Panoya veri koymak için bir HGLOBAL tutamacı gerekir.

`CSharedFile`bellek eşlenen dosyaları kullanmaz ve veriler işlemler arasında doğrudan paylaşılamaz.

`CSharedFile`nesneler otomatik olarak kendi bellek tahsis edebilirsiniz. Veya `CSharedFile` [CSharedFile::SetHandle'ı](#sethandle)arayarak nesneye kendi bellek bloğunuzu ekleyebilirsiniz. Her iki durumda da, bellek dosyasını otomatik `nGrowBytes`olarak büyütmek için `nGrowBytes` bellek sıfır değilse boyutlandırılmış artışlarla ayrılır.

Daha fazla bilgi için, *Çalışma Zamanı Kitaplığı Başvurusu'nda* [MFC'deki](../../mfc/files-in-mfc.md) Dosyalar ve [Dosya İşleme'deki](../../c-runtime-library/file-handling.md) dosyalara bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[Cmemfile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv.h

## <a name="csharedfilecsharedfile"></a><a name="csharedfile"></a>CSharedFile::CSharedFile

Bir `CSharedFile` nesne yi inşa eder ve bunun için bellek ayırır.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Parametreler

*nAllocFlags*<br/>
Belleğin nasıl ayrılacağını gösteren bayraklar. Geçerli bayrak değerlerinin listesi için [GlobalAlloc'a](/windows/win32/api/winbase/nf-winbase-globalalloc) bakın.

*nGrowBytes*<br/>
Baytlarda bellek ayırma artış.

## <a name="csharedfiledetach"></a><a name="detach"></a>CSharedFile::Detach

Bellek dosyasını kapatmak ve bellek bloğundan ayırmak için bu işlevi arayın.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek dosyasının içeriğini içeren bellek bloğunun tutamacı.

### <a name="remarks"></a>Açıklamalar

**Detach**tarafından döndürülen tutamacı kullanarak [SetHandle'ı](#sethandle)arayarak yeniden açabilirsiniz.

## <a name="csharedfilesethandle"></a><a name="sethandle"></a>CSharedFile::SetHandle

Nesneye genel bellek bloğu eklemek için `CSharedFile` bu işlevi çağırın.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hGlobalMemory*<br/>
Genel belleğe bağlı olmak için `CSharedFile`tutamak.

*bAllowGrow*<br/>
Bellek bloğunun büyümesine izin verilip verilmediğini belirtir.

### <a name="remarks"></a>Açıklamalar

*bAllowGrow* sıfır değilse, örneğin dosyaya bellek bloğunun boyutundan daha fazla bayt yazmaya çalışırsanız, bellek bloğunun boyutu gerektiği gibi artırılır.

## <a name="see-also"></a>Ayrıca bkz.

[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
