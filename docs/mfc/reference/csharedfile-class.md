---
title: CSharedFile sınıfı
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
ms.openlocfilehash: e86e64c1de232aba0c17a0fdfb3600e480567a57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324135"
---
# <a name="csharedfile-class"></a>CSharedFile sınıfı

[CMemFile](../../mfc/reference/cmemfile-class.md)-paylaşılan bellek dosyalarını destekleyen türetilmiş bir sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|Oluşturur bir `CSharedFile` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|Paylaşılan bellek dosyayı kapatır ve kendi bellek bloğu tanıtıcısını döndürür.|
|[CSharedFile::SetHandle](#sethandle)|Paylaşılan bellek dosyasına bir bellek bloğuna ekler.|

## <a name="remarks"></a>Açıklamalar

Dosya RAM yerine diskte depolanan dışında bellek dosyalarını disk dosyaları gibi davranır. Bellek dosyasını ham bayt aktarma veya hızlı bir geçici depolama için kullanışlı veya bağımsız işlemler arasında nesneleri seri hale getirilmiş.

Paylaşılan bellek dosyalarını, bunlar için bellek ile ayrılır, diğer bellek dosyalarından farklı [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows işlevi. `CSharedFile` Sınıfı bir küresel olarak ayrılan bellek bloğu içinde verileri depolar (kullanılarak oluşturulan `GlobalAlloc`), bu bellek bloğunda DDE, Pano veya diğer OLE/COM Tekdüzen veri aktarımı işlemleri, örneğin, kullanarak kullanarak paylaşılabilir `IDataObject`.

`GlobalAlloc` bir HGLOBAL işlemek yerine tarafından döndürülen işaretçi gibi bir bellek işaretçi döndürür [malloc](../../c-runtime-library/reference/malloc.md). Belirli uygulamalarda HGLOBAL işleyicisini gereklidir. Örneğin, verileri Pano'ya yerleştirme HGLOBAL işleyicisini gerekir.

Lütfen unutmayın `CSharedFile` kullanımı bellek eşlemeli dosyaları değil yapar ve verileri doğrudan işlemler arasında paylaşılamaz.

`CSharedFile` nesneleri otomatik olarak kendi bellek tahsis edin ya da kendi bellek bloğuna eklediğiniz `CSharedFile` çağırarak [CSharedFile::SetHandle](#sethandle). Her iki durumda da, bellek dosyası otomatik olarak büyüyen için bellek tahsis edilmez `nGrowBytes`-Artımlar, boyutlandırılmış `nGrowBytes` sıfır değil.

Daha fazla bilgi için bkz [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxadv.h

##  <a name="csharedfile"></a>  CSharedFile::CSharedFile

Oluşturur bir `CSharedFile` nesne ve onun için bellek ayırır.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Parametreler

*nAllocFlags*<br/>
Nasıl ayrılacak bellek olduğunu belirten bayrak. Bkz: [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) geçerli bayrak değerleri listesi.

*nGrowBytes*<br/>
Bayt cinsinden bellek ayırma artırma.

##  <a name="detach"></a>  CSharedFile::Detach

Bellek dosyayı kapatın ve bellek bloğundan ayırmak için bu işlevi çağırın.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek dosyasının içeriğini içeren bellek bloğu tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Çağırarak yeniden açabilirsiniz [SetHandle](#sethandle), tarafından döndürülen tanıtıcı kullanmanın **ayırma**.

##  <a name="sethandle"></a>  CSharedFile::SetHandle

İçin genel bellek bloğu eklemek için bu işlevi çağırın `CSharedFile` nesne.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hGlobalMemory*<br/>
Tanıtıcı eklenmesi için genel bellek `CSharedFile`.

*bAllowGrow*<br/>
Bellek bloğu büyümesine izin verilip verilmediğini belirtir.

### <a name="remarks"></a>Açıklamalar

Varsa *bAllowGrow* sıfır olmayan, bellek blok boyutu yükseltilmiştir gerekirse, örneğin, bir denemesi, daha fazla bayt bellek bloğu için ayrılan daha dosyaya yazmak için yapılır.

## <a name="see-also"></a>Ayrıca bkz.

[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
