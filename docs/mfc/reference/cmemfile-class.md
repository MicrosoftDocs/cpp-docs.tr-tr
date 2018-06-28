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
ms.openlocfilehash: e13c3b609a53e8c885e04530995a11218bf2704d
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040070"
---
# <a name="cmemfile-class"></a>CMemFile sınıfı
[CFile](../../mfc/reference/cfile-class.md)-türetilmiş sınıf bellek dosyalarını destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|Bellek dosya nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|Bellek bloğu iliştirir `CMemFile`.|  
|[CMemFile::Detach](#detach)|Bellekten bloğunu ayırır `CMemFile` ve ayrılmış bellek bloğu için bir işaretçi döndürür.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|Bellek ayırma davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Free](#free)|Bellek ayırmayı kaldırma davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::GrowFile](#growfile)|Bir dosya büyüyen zaman davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Memcpy](#memcpy)|Dosyaları okuma ve yazma, bellek kopyalama davranışını değiştirmek için geçersiz kılın.|  
|[CMemFile::Realloc](#realloc)|Bellek yeniden ayırma davranışını değiştirmek için geçersiz kılın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dosya RAM yerine diskte depolanan dışında bu bellek dosyaları disk dosyaları gibi davranır. Bellek dosyası veya bağımsız işlemler arasında nesneleri seri hale getirilmiş ham bayt aktarma veya hızlı geçici depolama için yararlı olur.  
  
 `CMemFile` nesneleri otomatik olarak kendi bellek ayırmak veya kendi bellek bloğu iliştirebilirsiniz `CMemFile` çağırarak nesne [Attach](#attach). Her iki durumda da, bellek dosyası otomatik olarak büyüyen için bellek tahsis edilir `nGrowBytes`-artışlarla, boyutta `nGrowBytes` sıfır değil.  
  
 Bellek bloğu etme işleminin otomatik olarak silinir `CMemFile` tarafından bellek başlangıçta ayrılmış ise nesne `CMemFile` ; Aksi halde, nesneye bağlı bellek ayırmayı kaldırma için sorumlu nesne.  
  
 Buradan ayırdığınızda sağlanan işaretçi üzerinden bellek bloğu erişebilirsiniz `CMemFile` çağırarak nesne [ayırma](#detach).  
  
 En yaygın kullanımı `CMemFile` oluşturmaktır bir `CMemFile` nesne ve çağırarak kullanmak [CFile](../../mfc/reference/cfile-class.md) üye işlevleri. Bu oluşturma Not bir `CMemFile` otomatik olarak açılır: çağrılmayan [CFile::Open](../../mfc/reference/cfile-class.md#open), yalnızca disk dosyaları için kullanılan. Çünkü `CMemFile` veri üyesi bir disk dosyasına kullanmadığı `CFile::m_hFile` kullanılmaz.  
  
 `CFile` Üye işlevleri [yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) için uygulanmadı `CMemFile`. Bu işlevler çağırırsanız bir `CMemFile` nesne alırsınız bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile` Çalışma Zamanı Kitaplığı işlevlerini kullanan [malloc](../../c-runtime-library/reference/malloc.md), [realloc](../../c-runtime-library/reference/realloc.md), ve [ücretsiz](../../c-runtime-library/reference/free.md) ayırmak için yeniden ayırın ve bellek; ve iç ayırması [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) okurken ve yazarken kopyalama bellek bloğu. Bu davranış veya davranışı değiştirmek isteyip istemediğinizi zaman `CMemFile` bir dosya büyür kendi sınıfından türetilen `CMemFile` ve uygun işlevleri geçersiz kılar.  
  
 Daha fazla bilgi için `CMemFile`, makalelerine bakın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [bellek yönetimi (MFC)](../../mfc/memory-management.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı Kitaplık Başvurusu*.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 Bu işlev tarafından çağrılır `CMemFile` üye işlevleri.  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBytes*  
 Ayrılan belleğin bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış olan bellek bloğu için bir işaretçi veya **NULL** ayırma başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek ayırma uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük ihtimalle geçersiz kılma istersiniz [serbest](#free) ve [Realloc](#realloc) de.  
  
 Varsayılan Uygulama çalışma zamanı kitaplığı işlevini kullanıyor [malloc](../../c-runtime-library/reference/malloc.md) bellek ayıramadı.  
  
##  <a name="attach"></a>  CMemFile::Attach  
 Bellek bloğu eklemek için bu işlevi çağırmak `CMemFile`.  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpBuffer*  
 İşaretçi eklenmiş arabellek `CMemFile`.  
  
 *nBufferSize*  
 Arabellek boyutunu bayt cinsinden belirten bir tamsayı.  
  
 *nGrowBytes*  
 Bellek ayırma artırma bayt.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu neden `CMemFile` bellek bloğu bellek dosyasını kullanın.  
  
 Varsa *nGrowBytes* 0 ' dır `CMemFile` dosya uzunluğu ayarlanacağını *nBufferSize*. İlişkili olduğu önce bellek bloğu verilerde buna `CMemFile` dosyası olarak kullanılır. Bu şekilde oluşturulan bellek dosyaları büyütülen olamaz.  
  
 Dosya büyütülmesi olamayacağından neden olmaz dikkatli olun `CMemFile` dosya büyütme girişimi için. Örneğin, çağrı yok `CMemFile` , geçersiz kılmalar [CFile:Write](../../mfc/reference/cfile-class.md#write) için sonunun yazma veya arama yok [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) daha uzun bir süre ile *nBufferSize*.  
  
 Varsa *nGrowBytes* 0'dan büyük `CMemFile` bağlı bellek bloğu içeriğini göz ardı eder. Kullanılarak sıfırdan bellek dosyanın içeriğini yazmak zorunda kalırsınız `CMemFile` , geçersiz kılma `CFile::Write`. Dosya sonunun yazmak veya çağırarak dosya büyütme çalışırsanız `CMemFile` , geçersiz kılma `CFile::SetLength`, `CMemFile` artışlarla bellek ayırma büyüyecektir *nGrowBytes*. Bellek ayırma büyüyen başarısız olur bellek bloğu için geçirirseniz `Attach` ile uyumlu bir yöntem ile ayrılan değildi [ayırma](#alloc). Varsayılan uygulaması ile uyumlu olacak şekilde `Alloc`, çalışma zamanı kitaplığı işlevi bellekle ayırmalısınız [malloc](../../c-runtime-library/reference/malloc.md) veya [calloc](../../c-runtime-library/reference/calloc.md).  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 İlk aşırı boş bellek dosyasını açar.  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGrowBytes*  
 Bellek ayırma artırma bayt.  
  
 *lpBuffe*r  
 İşaretçi boyutu bilgilerinin alan arabellek *nBufferSize*.  
  
 *nBufferSize*  
 Dosya arabellek boyutunu bayt cinsinden belirten bir tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya oluşturucusu tarafından açılmış ve, değil çağırmalıdır Not [CFile::Open](../../mfc/reference/cfile-class.md#open).  
  
 İlk Oluşturucusu kullanılan ve hemen adlı gibi ikinci aşırı aynı davranır [Attach](#attach) aynı parametrelere sahip. Bkz: `Attach` Ayrıntılar için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 Tarafından kullanılan bellek bloğu için bir işaretçi almak için bu işlevi çağırmak `CMemFile`.  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek dosyasının içeriğini içeren bellek bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev de kapanır çağırma `CMemFile`. Bellek bloğuna iliştirebilirsiniz `CMemFile` çağırarak [Attach](#attach). Dosyayı yeniden bağlayın ve verileri kullanmak istiyorsanız, çağırmalıdır [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) çağırmadan önce dosya uzunluğu almak için `Detach`. Bellek bloğuna eklerseniz unutmayın `CMemFile` verileri kullanabilmesi için ( `nGrowBytes` == 0), bellek dosya büyütme açamayacaksınız sonra.  
  
##  <a name="free"></a>  CMemFile::Free  
 Bu işlev tarafından çağrılır `CMemFile` üye işlevleri.  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMem*  
 Bırakılmasına bellek işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek ayırmayı kaldırma uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük ihtimalle geçersiz kılma istersiniz [ayırma](#alloc) ve [Realloc](#realloc) de.  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 Bu işlev, birkaçı tarafından çağrılır `CMemFile` üye işlevleri.  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwNewLen*  
 Yeni bellek dosyası boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Değiştirmek istiyorsanız kılabilirsiniz nasıl `CMemFile` dosya büyür. Varsayılan Uygulama çağrıları [Realloc](#realloc) mevcut bloğu büyümeye (veya [ayırma](#alloc) bir bellek bloğu oluşturmak için), katları bellek ayırmak `nGrowBytes` oluşturucuda belirtilen değeri veya [Attach](#attach) çağırın.  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 Bu işlev tarafından çağrılır `CMemFile` , geçersiz kılmalar [CFile::Read](../../mfc/reference/cfile-class.md#read) ve [CFile::Write](../../mfc/reference/cfile-class.md#write) bellek dosyası gelen ve giden veri aktarımı için.  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMemTarget*  
 Kaynak bellek kopyalanacak dosyaların bellek bloğu işaretçi.  
  
 *lpMemSource*  
 Kaynak bellek bloğu işaretçi.  
  
 *nBytes*  
 Kopyalanacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını *lpMemTarget*.  
  
### <a name="remarks"></a>Açıklamalar  
 Şeklini değiştirmek istiyorsanız, bu işlevi geçersiz kılma, `CMemFile` bu bellek kopyaları yapar.  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
 Bu işlev tarafından çağrılır `CMemFile` üye işlevleri.  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpMem*  
 Ayrılabilecek için bellek bloğu için bir işaretçi.  
  
 *nBytes*  
 Yeni bellek bloğu boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bırakılan (ve muhtemelen taşınmış), bellek bloğu için bir işaretçi veya **NULL** yeniden ayırma işlemi başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bellek yeniden ayırma uygulamak için bu işlevi geçersiz kılar. Bu işlev geçersiz kılarsanız, büyük ihtimalle geçersiz kılma istersiniz [ayırma](#alloc) ve [serbest](#free) de.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



