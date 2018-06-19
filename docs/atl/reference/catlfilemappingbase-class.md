---
title: CAtlFileMappingBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e315a29f72c887b5bff2e8177e7a47aed18c3fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364450"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase sınıfı
Bu sınıf, bellekle eşlenen bir dosyayı temsil eder.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Oluşturucu.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Bir dosya eşleme nesneden kopyalamak için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::GetData](#getdata)|Bir dosya eşleme nesnesinden verileri almak için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Dosya tanıtıcısı döndürmek için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Bir dosya eşleme nesnesi eşleme boyutu almak için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Tüm işlemlere tam erişimi veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Dosya eşleme nesnesi için bir işleyiciyi döndürmek için bu yöntemi çağırın.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Bir dosya eşleme nesnesi eşlemeyi kaldırmak için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Geçerli dosya eşleme nesnesi başka bir dosya eşleme nesnesine ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dosyanın içeriğini bir işlemin sanal adres alanının bir bölümü ile dosya eşleme ilişkidir. Bu sınıf, programların kolayca erişmek ve veri paylaşımına izin dosya eşleme nesnesi oluşturmak için yöntemler sağlar.  
  
 Daha fazla bilgi için bkz: [eşleme dosyasını](http://msdn.microsoft.com/library/windows/desktop/aa366556) Windows SDK.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase  
 Oluşturucu.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `orig`  
 Yeni nesne oluşturmak için kopyalamak için özgün dosya eşleme nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İsteğe bağlı olarak var olan bir nesne kullanarak yeni bir dosya eşleme nesnesi oluşturur. Çağırmak hala gereklidir [CAtlFileMappingBase::MapFile](#mapfile) veya belirli bir dosya için dosya eşleme nesnesi oluşturulamadı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Yok Edicisi.  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf ve çağrıları tarafından ayrılan tüm kaynakları serbest bırakır [CAtlFileMappingBase::Unmap](#unmap) yöntemi.  
  
##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom  
 Bir dosya eşleme nesneden kopyalamak için bu yöntemi çağırın.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `orig`  
 Kopyalanacak özgün dosya eşleme nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
##  <a name="getdata"></a>  CAtlFileMappingBase::GetData  
 Bir dosya eşleme nesnesinden verileri almak için bu yöntemi çağırın.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi verileri döndürür.  
  
##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle  
 Dosya eşleme nesnesi için bir işleyiciyi döndürmek için bu yöntemi çağırın.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tanıtıcı dosya eşleme nesnesi döndürür.  
  
##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize  
 Bir dosya eşleme nesnesi eşleme boyutu almak için bu yöntemi çağırın.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleme boyutu döndürür.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile  
 Açmak veya belirtilen dosya için bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hFile`  
 Bir eşleme nesnesi oluşturulacağı dosyaya işleyin. `hFile` geçerli olmalıdır ve INVALID_HANDLE_VALUE için ayarlanamaz.  
  
 `nMappingSize`  
 Eşleme boyutu. 0 ise, dosya eşleme nesnesi en büyük boyutu tarafından tanımlanan dosya boyutunu eşittir *Hfıle.*  
  
 `nOffset`  
 Başlamak için eşleme olduğu dosya uzaklığı. Uzaklık değeri sistemin bellek ayırma ayrıntı katı olmalıdır.  
  
 `dwMappingProtection`  
 Dosya eşlendiğinde dosya görünümü için istenen koruma. Bkz: `flProtect` içinde [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) Windows SDK.  
  
 `dwViewDesiredAccess`  
 Dosya görünümü ve bu nedenle, dosyasıyla eşleştirilmiş sayfaları koruma erişim türünü belirtir. Bkz: `dwDesiredAccess` içinde [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dosya eşleme nesnesi oluşturulduktan sonra dosyanın boyutu dosya eşleme nesnesinin boyutunu aşmamalıdır; varsa, tüm dosyanın içeriğini paylaşmak için kullanılabilir. Daha fazla ayrıntı için bkz: [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) ve [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem  
 Tüm işlemlere tam erişimi veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.  
  
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
 `nMappingSize`  
 Eşleme boyutu. 0 ise, en fazla dosya eşleme nesnesi tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşit boyutudur `szName.`  
  
 `szName`  
 Eşleme nesnesinin adı.  
  
 *pbAlreadyExisted*  
 TRUE ise eşleme nesnesi zaten ayarlanmış bir Boole değeri noktalarına vardı.  
  
 `lpsa`  
 İşaretçi bir **SECURITY_ATTRIBUTES** yapısı alt işlemleri tarafından döndürülen tanıtıcı devralınan olup olmadığını belirler. Bkz: *lpAttributes* içinde [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) Windows SDK'sındaki.  
  
 `dwMappingProtection`  
 Dosya eşlendiğinde dosya görünümü için istenen koruma. Bkz: `flProtect` içinde **CreateFileMapping** Windows SDK.  
  
 `dwViewDesiredAccess`  
 Dosya görünümü ve bu nedenle, dosyasıyla eşleştirilmiş sayfaları koruma erişim türünü belirtir. Bkz: `dwDesiredAccess` içinde [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 **MapShareMem** tarafından oluşturulan bir var olan dosya eşleme nesnesi verir [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), işlemler arasında paylaşılacak.  
  
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
 `szName`  
 Eşleme nesnesinin adı. Bu adda bir dosya eşleme nesnesi için açık bir tanıtıcı ve eşleme nesnesinde güvenlik tanımlayıcısı ile çakışmaması `dwViewDesiredAccess` parametresi açma işlemi başarılı olur.  
  
 `nMappingSize`  
 Eşleme boyutu. 0 ise, en fazla dosya eşleme nesnesi tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşit boyutudur `szName.`  
  
 `nOffset`  
 Başlamak için eşleme olduğu dosya uzaklığı. Uzaklık değeri sistemin bellek ayırma ayrıntı katı olmalıdır.  
  
 `dwViewDesiredAccess`  
 Dosya görünümü ve bu nedenle, dosyasıyla eşleştirilmiş sayfaları koruma erişim türünü belirtir. Bkz: `dwDesiredAccess` içinde [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, onaylama işlemi hata ortaya giriş parametreleri geçersiz.  
  
##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =  
 Geçerli dosya eşleme nesnesi başka bir dosya eşleme nesnesine ayarlar.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Parametreler  
 `orig`  
 Geçerli dosya eşleme nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesne için bir başvuru döndürür.  
  
##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap  
 Bir dosya eşleme nesnesi eşlemeyi kaldırmak için bu yöntemi çağırın.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarı veya hata `HRESULT` hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) daha fazla ayrıntı için Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlFileMapping sınıfı](../../atl/reference/catlfilemapping-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
