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
ms.openlocfilehash: 74a34ec169868d3e28f78f33da38dbda21ef23b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502608"
---
# <a name="csharedfile-class"></a>CSharedFile sınıfı

Paylaşılan bellek dosyalarını destekleyen [CMemFile](../../mfc/reference/cmemfile-class.md)ile türetilmiş sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSharedFile:: CSharedFile](#csharedfile)|Bir `CSharedFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSharedFile::D etach](#detach)|Paylaşılan bellek dosyasını kapatır ve bellek bloğunun tanıtıcısını döndürür.|
|[CSharedFile:: SetHandle](#sethandle)|Paylaşılan bellek dosyasını bir bellek bloğuna iliştirir.|

## <a name="remarks"></a>Açıklamalar

Bellek dosyaları disk dosyaları gibi davranır. Fark, bir bellek dosyasının disk yerine RAM 'e depolanmasıdır. Bellek dosyası hızlı geçici depolama için veya bağımsız süreçler arasında ham baytları veya seri hale getirilmiş nesnelerin aktarılması için yararlıdır.

Paylaşılan bellek dosyaları, [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows işleviyle ayrılmaları için bellekteki diğer bellek dosyalarından farklıdır. Sınıfı, verileri genel olarak ayrılmış bir bellek bloğunda (kullanılarak `GlobalAlloc`oluşturulur) depolar ve bu bellek bloğu, örneğin kullanarak `IDataObject`DDE, pano veya diğer ole/com Tekdüzen veri aktarımı işlemleri kullanılarak paylaşılabilir. `CSharedFile`

`GlobalAlloc`[malloc](../../c-runtime-library/reference/malloc.md)tarafından döndürülen işaretçi gibi bir bellek işaretçisi yerıne BIR HGLOBAL tanıtıcı döndürür. HGLOBAL tanıtıcısı belirli uygulamalarda gereklidir. Örneğin, panoya veri koymak için bir HGLOBAL tanıtıcısı gerekir.

`CSharedFile`bellekle eşlenen dosyaları kullanmaz ve veriler doğrudan süreçler arasında paylaştırılamaz.

`CSharedFile`nesneler, kendi belleğini otomatik olarak ayırabilir. Ya da, [CSharedFile:: SetHandle](#sethandle)öğesini `CSharedFile` çağırarak kendi bellek blobunu nesnesine ekleyebilirsiniz. Her iki durumda da, sıfır `nGrowBytes` `nGrowBytes` değilse bellek dosyası otomatik olarak büyümeye yönelik bellek, boyutlandırılmış artışlarla ayrılır.

Daha fazla bilgi için bkz. [MFC 'Deki dosyalar](../../mfc/files-in-mfc.md) ve *çalışma zamanı kitaplığı başvurusunda* [Dosya işleme](../../c-runtime-library/file-handling.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxadv. h

##  <a name="csharedfile"></a>CSharedFile:: CSharedFile

Bir `CSharedFile` nesne oluşturur ve bellek ayırır.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Parametreler

*nAllocFlags*<br/>
Belleğin nasıl ayrılacağını gösteren Bayraklar. Geçerli bayrak değerlerinin listesi için bkz. [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) .

*nGrowBytes*<br/>
Bayt cinsinden bellek ayırma artışı.

##  <a name="detach"></a>CSharedFile::D etach

Bellek dosyasını kapatmak ve bellek bloğundan ayırmak için bu işlevi çağırın.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bellek dosyasının içeriğini içeren bellek bloğunun tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

**Ayırma**ile döndürülen tanıtıcıyı kullanarak [SetHandle](#sethandle)çağırarak yeniden açabilirsiniz.

##  <a name="sethandle"></a>CSharedFile:: SetHandle

`CSharedFile` Nesneye bir genel bellek bloğu iliştirmek için bu işlevi çağırın.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hGlobalMemory*<br/>
Öğesine eklenecek genel belleği işleyin `CSharedFile`.

*bAllowGrow*<br/>
Bellek bloğunun büyümesine izin verilip verilmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

*BAllowGrow* sıfırdan büyükse, bellek bloğunun boyutu gerektiği gibi artar, örneğin, dosyaya bellek bloğunun boyutundan daha fazla bayt yazmayı denerseniz.

## <a name="see-also"></a>Ayrıca bkz.

[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
