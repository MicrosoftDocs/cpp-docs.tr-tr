---
title: CMemFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3584568196fbccc9bab33ea3b51e876e174cbd18
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336600"
---
# <a name="cmemfile-class"></a>CMemFile sınıfı
[CFile](../../mfc/reference/cfile-class.md)-türetilmiş bellek dosyalarını destekleyen bir sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Bellek, dosya bir nesne oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Bir bellek bloğunu ekler `CMemFile`.|  
|[CMemFile::Detach](#detach)|Bellek bloğu ayırır `CMemFile` ve ayrılmış bellek bloğu için bir işaretçi döndürür.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Bellek ayırma davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Free](#free)|Bellek ayırmayı kaldırma davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::GrowFile](#growfile)|Bir dosyası büyürken davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Memcpy](#memcpy)|Dosyaları okuma ve yazma, bellek kopyalama davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Realloc](#realloc)|Bellek reallocation davranışını değiştirmek için geçersiz kılın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dosya RAM yerine diskte depolanan dışında bu bellek dosyaları disk dosyaları gibi davranır. Bellek dosyasını ham bayt aktarma veya hızlı bir geçici depolama için kullanışlı veya bağımsız işlemler arasında nesneleri seri hale getirilmiş.  
  
 `CMemFile` nesneleri otomatik olarak kendi bellek tahsis edin ya da kendi bellek bloğuna eklediğiniz `CMemFile` çağırarak [iliştirme](#attach). Her iki durumda da, bellek dosyası otomatik olarak büyüyen için bellek tahsis edilmez `nGrowBytes`-Artımlar, boyutlandırılmış `nGrowBytes` sıfır değil.  
  
 Bellek bloğu yok etme sırasında otomatik olarak silinecek `CMemFile` tarafından bellek başlangıçta ayrılan, nesne `CMemFile` nesne; Aksi halde, nesneye bağlı belleğini için sorumlu olursunuz.  
  
 Bellek bloğu ondan ayırdığınızda sağlanan işaretçisi aracılığıyla erişebileceğiniz `CMemFile` çağırarak [ayırma](#detach).  
  
 En yaygın kullanımı `CMemFile` oluşturmaktır bir `CMemFile` çağırarak kullanın ve nesne [CFile](../../mfc/reference/cfile-class.md) üye işlevleri. Bu oluşturma Not bir `CMemFile` otomatik olarak açılır: çağrılmayan [CFile::Open](../../mfc/reference/cfile-class.md#open), yalnızca disk dosyaları için kullanılan. Çünkü `CMemFile` veri üyesi bir disk dosyası kullanmaz `CFile::m_hFile` kullanılmaz.  
  
 `CFile` Üye işlevleri [yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) için uygulanmadı `CMemFile`. Bu işlevler çağırırsanız bir `CMemFile` nesnesi elde edersiniz bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` çalışma zamanı kitaplık işlevleri kullanan [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), ve [ücretsiz](../../c-runtime-library/reference/free.md) ayırmak için yeniden ayırın ve bellek; ve iç serbest [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) okurken ve yazarken kopyalama bellek bloğu. Bu davranış veya davranışını değiştirmek istiyorsanız, `CMemFile` bir dosya büyüdükçe kendi sınıfından türetilir `CMemFile` ve uygun işlevleri geçersiz kılar.  
  
 Daha fazla bilgi için `CMemFile`, makalelere göz atın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [bellek yönetimi (MFC)](../../mfc/memory-management.md) görüp [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı Kitaplık Başvurusu*.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 Bu işlevi çağıran `CMemFile` üye işlevleri.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBytes*  
 Ayrılacak bellek bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılan bellek bloğuna işaretçi veya ayırma başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek ayırma uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük olasılıkla geçersiz kılmak isteyebilirsiniz [ücretsiz](#free) ve [Realloc](#realloc) de.  
  
 Varsayılan Uygulama çalışma zamanı kitaplığı işlevi kullanır [malloc](../../c-runtime-library/reference/malloc.md) bellek ayrılamadı.  
  
##  <a name="attach"></a>  CMemFile::Attach  
 Bir bellek bloğunu eklemek için bu işlevi çağırın `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpBuffer*  
 Eklenmesi için arabellek için işaretçi `CMemFile`.  
  
 *nBufferSize*  
 Arabellek boyutu bayt cinsinden belirten bir tamsayı.  
  
 *nGrowBytes*  
 Bayt cinsinden bellek ayırma artırma.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu neden `CMemFile` bellek bloğunu bellek dosyası olarak kullanılacak.  
  
 Varsa *nGrowBytes* 0 ' dır `CMemFile` dosya uzunluğu ayarlayacak *nBufferSize*. Depolamaya bağlanmıştır önce bu verileri bellek bloğu anlamına `CMemFile` dosyası olarak kullanılır. Bu şekilde oluşturulan bellek dosyalarını büyütmüş olamaz.  
  
 Dosya büyütülmesi olamayacağından neden dikkat `CMemFile` dosya büyütme girişimi için. Örneğin, çağırmaz `CMemFile` , geçersiz kılar [CFile:Write](../../mfc/reference/cfile-class.md#write) için sonunun yazma veya Remove() çağırmayın [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) daha uzun bir süre ile *nBufferSize*.  
  
 Varsa *nGrowBytes* 0'dan büyükse `CMemFile` bağlı bellek bloğu içeriğini yoksayar. Bellek dosyasının içeriğini kullanılarak sıfırdan yazmak zorunda kalırsınız `CMemFile` , geçersiz kılma `CFile::Write`. Dosyanın sonundan yazma veya çağırarak dosya büyütme denerseniz `CMemFile` , geçersiz kılma `CFile::SetLength`, `CMemFile` artışlarla bellek ayırma büyüyecektir *nGrowBytes*. Artan bellek ayırma başarısız olur bellek bloğu için geçirirseniz `Attach` ile uyumlu bir yöntem atanmadı [ayırma](#alloc). Varsayılan uygulaması ile uyumlu olacak şekilde `Alloc`, çalışma zamanı kitaplığı işlevi bellekle ayırmalısınız [malloc](../../c-runtime-library/reference/malloc.md) veya [calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 İlk aşırı yükleme, bir boş bellek dosyası açılır.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGrowBytes*  
 Bayt cinsinden bellek ayırma artırma.  
  
 *lpBuffe*r  
 Boyut bilgileri alan arabellek için işaretçi *nBufferSize*.  
  
 *nBufferSize*  
 Dosya arabellek boyutu bayt cinsinden belirten bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya Oluşturucu tarafından açılmış ve, çağırmamalıdır Not [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 İlk Oluşturucu kullanılan ve çağrıldıktan hemen gibi ikinci aşırı yükleme aynı davranır [iliştirme](#attach) aynı parametrelere sahip. Bkz: `Attach` Ayrıntılar için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 Tarafından kullanılan bellek bloğuna işaretçi almak için bu işlevi çağırın `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek dosyasının içeriğini içeren bellek bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ayrıca kapanır çağırma `CMemFile`. Bellek bloğuna iliştirebilirsiniz `CMemFile` çağırarak [iliştirme](#attach). Dosyayı yeniden bağlayın ve verileri kullanmak istiyorsanız, çağırmalıdır [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) çağırmadan önce dosya uzunluğunu almak için `Detach`. Bir bellek bloğuna eklediğiniz gerçekleştiriyorsanız `CMemFile` verilerini kullanabilmesi için ( `nGrowBytes` == 0), sonra da bellek dosya büyütme mümkün olmayacaktır.  
  
##  <a name="free"></a>  CMemFile::Free  
 Bu işlevi çağıran `CMemFile` üye işlevleri.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMem*  
 Serbest bırakılması bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek ayırmayı kaldırma uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük olasılıkla geçersiz kılmak isteyebilirsiniz [ayırma](#alloc) ve [Realloc](#realloc) de.  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 Bu işlev tarafından birkaç çağrılır `CMemFile` üye işlevleri.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwNewLen*  
 Bellek dosya yeni boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Değiştirmek istiyorsanız kılabilirsiniz nasıl `CMemFile` kendi dosya büyür. Varsayılan Uygulama çağrıları [Realloc](#realloc) mevcut bloğu büyümesine (veya [ayırma](#alloc) bir bellek bloğu oluşturmak için), katları bellek ayırma `nGrowBytes` oluşturucuda belirtilen değeri veya [İliştirme](#attach) çağırın.  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 Bu işlevi çağıran `CMemFile` , geçersiz kılmalar [CFile::Read](../../mfc/reference/cfile-class.md#read) ve [CFile::Write](../../mfc/reference/cfile-class.md#write) bellek dosyası gelen ve giden veri aktarımı için.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMemTarget*  
 Kaynak bellek kopyalanır bellek bloğuna işaretçi.  
  
 *lpMemSource*  
 Kaynak bellek bloğuna işaretçi.  
  
 *nBytes*  
 Kopyalanacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını *lpMemTarget*.  
  
### <a name="remarks"></a>Açıklamalar  
 Şeklini değiştirmek istiyorsanız, bu işlev geçersiz kılma, `CMemFile` bu bellek kopyalar yapar.  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
 Bu işlevi çağıran `CMemFile` üye işlevleri.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMem*  
 Ayrılabilecek bellek bloğuna işaretçi.  
  
 *nBytes*  
 Bellek bloğu için yeni boyut.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bırakılan (ve muhtemelen taşındı), bellek bloğu için bir işaretçi ya da yeniden ayırma başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek reallocation uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük olasılıkla geçersiz kılmak isteyebilirsiniz [ayırma](#alloc) ve [ücretsiz](#free) de.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



