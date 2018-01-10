---
title: "CSharedFile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs: C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27c749f86f9e3fbd310fd03b3a82768d58632087
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csharedfile-class"></a>CSharedFile sınıfı
[CMemFile](../../mfc/reference/cmemfile-class.md)-destekleyen türetilmiş bir sınıf paylaşılan bellek dosyaları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Oluşturan bir `CSharedFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Paylaşılan bellek dosyası kapatır ve kendi bellek bloğu işleyicisini döndürür.|  
|[CSharedFile::SetHandle](#sethandle)|Paylaşılan bellek dosyası bir bellek bloğu ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dosya RAM yerine disk üzerinde depolanır bellek dosyaları disk dosyaları gibi davranır. Bellek dosyası veya bağımsız işlemler arasında nesneleri seri hale getirilmiş ham bayt aktarma veya hızlı geçici depolama için yararlı olur.  
  
 Paylaşılan bellek dosyalar, bunlar için bellek tahsis edilen, diğer bellek dosyalarından farklı [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows işlevi. `CSharedFile` Sınıfı bir genel ayrılmış bellek bloğu içinde veri depolar (kullanılarak oluşturulan **GlobalAlloc**), ve bu bellek bloğu DDE, Pano veya diğer OLE/COM Tekdüzen veri aktarımı işlemlerini, örneğin, kullanılarak paylaşılabilir. kullanarak `IDataObject`.  
  
 **GlobalAlloc** döndüren bir `HGLOBAL` işlemek bellek tarafından döndürülen işaretçi gibi bir işaretçi yerine [malloc](../../c-runtime-library/reference/malloc.md). `HGLOBAL` Tanıtıcısı belirli uygulamalarda gereklidir. Örneğin, veri yerleştirilecek Pano ihtiyacınız bir `HGLOBAL` işler.  
  
 Lütfen unutmayın `CSharedFile` değil bellekle eşlenen kullanım dosyalar yapar ve verileri doğrudan işlemler arasında paylaşılamaz.  
  
 `CSharedFile`nesneleri otomatik olarak kendi bellek ayırmak veya kendi bellek bloğu iliştirebilirsiniz `CSharedFile` çağırarak nesne [CSharedFile::SetHandle](#sethandle). Her iki durumda da, bellek dosyası otomatik olarak büyüyen için bellek tahsis edilir `nGrowBytes`-artışlarla, boyutta `nGrowBytes` sıfır değil.  
  
 Daha fazla bilgi için bkz: [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxadv.h  
  
##  <a name="csharedfile"></a>CSharedFile::CSharedFile  
 Oluşturan bir `CSharedFile` nesne ve bunun için bellek ayırır.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Parametreler  
 *nAllocFlags*  
 Nasıl ayrılacak bellek olduğunu belirten işaretler. Bkz: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) geçerli bayrak değerleri listesi.  
  
 `nGrowBytes`  
 Bellek ayırma artırma bayt.  
  
##  <a name="detach"></a>CSharedFile::Detach  
 Bellek dosyayı kapatın ve bellek bloğundan ayırmak için bu işlevini çağırın.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek dosyasının içeriğini içeren bellek bloğu işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak yeniden açabilirsiniz [SetHandle](#sethandle), tarafından döndürülen işleci kullanılarak **ayırma**.  
  
##  <a name="sethandle"></a>CSharedFile::SetHandle  
 Bir genel bellek bloğu eklemek için bu işlevi çağırmak `CSharedFile` nesnesi.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *hGlobalMemory*  
 Eklenmesi için genel bellek tanıtıcı `CSharedFile`.  
  
 `bAllowGrow`  
 Bellek bloğu büyümeye izin verilip verilmediğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bAllowGrow` sıfır olmayan, bellek bloğu boyutu yükseltilmiştir gerekirse, örneğin, bir deneme olursa daha fazla bayt bellek bloğu için ayrılan daha dosyaya yazmak için yapılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMemFile sınıfı](../../mfc/reference/cmemfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
