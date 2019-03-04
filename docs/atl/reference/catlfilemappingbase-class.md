---
title: CAtlFileMappingBase sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: d31bc72e485fbb15ed595a7c777c3685a00865c4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270145"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase sınıfı

Bu sınıf, bir bellek işlemeli dosya temsil eder.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlFileMappingBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Oluşturucu.|
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Bir dosya eşlemesi nesneden kopyalamak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::GetData](#getdata)|Bir dosya eşlemesi nesnesinden verileri almak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::GetHandle](#gethandle)|Dosya tanıtıcısı döndürmek için bu yöntemi çağırın.|
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Bir dosya eşlemesi nesneden eşleme boyutunu almak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::MapFile](#mapfile)|Bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Tüm işlemlere tam erişim veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Dosya eşleme nesnesi için bir tanıtıcı döndürmek için bu yöntemi çağırın.|
|[CAtlFileMappingBase::Unmap](#unmap)|Bir dosya eşleme nesnesi eşlemeyi kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::operator =](#operator_eq)|Geçerli dosya eşleme nesnesi başka bir dosya eşleme nesnesi olarak ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir dosyanın içeriğini bir işlemin sanal adres alanının bir bölümü ile dosya eşlemesi işbirliğidir. Bu sınıf, kolayca erişme ve veri paylaşma olanağı programlar izin veren Dosya eşleme nesnesi oluşturmak için yöntemleri sağlar.

Daha fazla bilgi için [eşleme dosyası](/windows/desktop/Memory/file-mapping) Windows SDK.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlfile.h

##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase

Oluşturucu.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Parametreler

*ORIG*<br/>
Yeni nesne oluşturma kopyalamak için orijinal dosya eşleme nesnesi.

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı olarak var olan bir nesneyi kullanarak yeni bir dosya eşleme nesnesi oluşturur. Çağırmak hala gereklidir [CAtlFileMappingBase::MapFile](#mapfile) açın ya da belirli bir dosya için dosya eşleme nesnesi oluşturun.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase

Yıkıcı.

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf ve çağrıları tarafından ayrılan tüm kaynakları serbest bırakan [CAtlFileMappingBase::Unmap](#unmap) yöntemi.

##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom

Bir dosya eşlemesi nesneden kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Parametreler

*ORIG*<br/>
Kopyalamak için orijinal dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getdata"></a>  CAtlFileMappingBase::GetData

Bir dosya eşlemesi nesnesinden verileri almak için bu yöntemi çağırın.

```
void* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Verisine bir işaretçi döndürür.

##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle

Dosya eşleme nesnesi için bir tanıtıcı döndürmek için bu yöntemi çağırın.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya eşleme nesnesi için bir tanıtıcı döndürür.

##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize

Bir dosya eşlemesi nesneden eşleme boyutunu almak için bu yöntemi çağırın.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme boyutu döndürür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile

Belirtilen dosya için bir dosya eşleme nesnesi oluşturun veya açın için bu yöntemi çağırın.

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>Parametreler

*Hfıle*<br/>
Eşleme nesnesi oluşturulacağı dosyasına işleyin. *Hfıle* geçerli olmalıdır ve INVALID_HANDLE_VALUE için ayarlanamaz.

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin boyutu tarafından tanımlanan dosyaya geçerli boyutuna eşit olan *Hfıle.*

*nOffset*<br/>
Başlamak için eşleme olduğu dosya uzaklığı. Uzaklık değeri, sistemin bellek ayırma tanecikliliğinin bir katı olmalıdır.

*dwMappingProtection*<br/>
Dosya görünümü için dosya eşlendiğinde istenen koruma. Bkz: *flProtect* içinde [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) Windows SDK.

*dwViewDesiredAccess*<br/>
Dosya görünümü ve bu nedenle, dosya tarafından eşleştirilen sayfalarının koruma erişim türünü belirtir. Bkz: *dwDesiredAccess* içinde [MapViewOfFileEx](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bir dosya eşleme nesnesi oluşturulduktan sonra dosyanın boyutu dosya eşleme nesnesinin boyutu aşmamalıdır; varsa, dosya içeriğinin tamamını paylaşmak için kullanılabilir. Daha fazla ayrıntı için [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) ve [MapViewOfFileEx](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem

Tüm işlemlere tam erişim veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.

```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parametreler

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin boyutu tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşit olan *szName*.

*szName*<br/>
Eşleme nesnesinin adı.

*pbAlreadyExisted*<br/>
Gerekirse TRUE eşleme nesnesi zaten ayarlanmış bir BOOL değeri noktalarına vardı.

*lpsa*<br/>
İşaretçiyi bir `SECURITY_ATTRIBUTES` döndürülen tanıtıcının alt işlemler tarafından devralınıp alınmayacağını belirleyen yapısı. Bkz: *lpAttributes* içinde [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) Windows SDK.

*dwMappingProtection*<br/>
Dosya görünümü için dosyanın eşlendiğinde istenen koruma. Bkz: *flProtect* içinde `CreateFileMapping` Windows SDK.

*dwViewDesiredAccess*<br/>
Dosya görünümü ve bu nedenle, dosya tarafından eşleştirilen sayfalarının koruma erişim türünü belirtir. Bkz: *dwDesiredAccess* içinde [MapViewOfFileEx](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

`MapShareMem` tarafından oluşturulan mevcut bir dosya eşleme nesnesinin sağlar [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga), işlemler arasında paylaşılacak.

##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping

Belirtilen dosya için bir adlandırılmış dosya eşleme nesnesi açmak için bu yöntemi çağırın.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parametreler

*szName*<br/>
Eşleme nesnesinin adı. Varsa bu adda bir dosya eşleme nesnesi açık bir tanıtıcısı ve eşleme nesnesinde güvenlik tanımlayıcısı ile çakışmaz *dwViewDesiredAccess* parametresi açma işlemi başarılı olur.

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin boyutu tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşit olan *szName*.

*nOffset*<br/>
Başlamak için eşleme olduğu dosya uzaklığı. Uzaklık değeri, sistemin bellek ayırma tanecikliliğinin bir katı olmalıdır.

*dwViewDesiredAccess*<br/>
Dosya görünümü ve bu nedenle, dosya tarafından eşleştirilen sayfalarının koruma erişim türünü belirtir. Bkz: *dwDesiredAccess* içinde [MapViewOfFileEx](/windows/desktop/api/memoryapi/nf-memoryapi-mapviewoffileex) Windows SDK.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Giriş parametreleri geçersiz olduğunda, hata ayıklama yapılarında, onaylama işlemi hatası oluşur.

##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =

Geçerli dosya eşleme nesnesi başka bir dosya eşleme nesnesi olarak ayarlar.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Parametreler

*ORIG*<br/>
Geçerli dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru döndürür.

##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap

Bir dosya eşleme nesnesi eşlemeyi kaldırmak için bu yöntemi çağırın.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [UnmapViewOfFile](/windows/desktop/api/memoryapi/nf-memoryapi-unmapviewoffile) daha fazla ayrıntı için Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMapping Sınıfı](../../atl/reference/catlfilemapping-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
