---
title: CStdioFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 868442a2936781ed24588f47dcb591cadcc48f0d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="cstdiofile-class"></a>CStdioFile Class
Çalışma zamanı işlevi tarafından açılan C çalışma zamanı akışı dosyasını temsil eder [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|Oluşturan bir `CStdioFile` bir yol veya dosya işaretçi nesnesinden.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|Fazla Yüklendi. Açık varsayılan ile kullanılmak üzere tasarlanmıştır `CStdioFile` Oluşturucusu (geçersiz kılmaları [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|Tek satırlık metin okur.|  
|[CStdioFile::Seek](#seek)|Geçerli dosya işaretçisini yerleştirir.|  
|[CStdioFile::WriteString](#writestring)|Tek satırlık metin yazar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|Açık bir dosyayı gösteren bir işaretçi içeriyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Akışı dosyalarını arabelleğe alınmış ve metin modunda (varsayılan) veya ikili mod açılabilir.  
  
 Metin modunu satır başı satır besleme çiftleri için özel işlem sağlar. Bir satır başı karakteri yazdığınız zaman metin moduna (0x0A) karakter `CStdioFile` nesnesi, bayt çifti (0x0D, 0x0A) dosyasına gönderilir. Okurken, bayt çifti (0x0D, 0x0A) tek bir 0x0A bayt çevrilir.  
  
 [CFile](../../mfc/reference/cfile-class.md) işlevleri [yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) için desteklenmeyen `CStdioFile`.  
  
 Bu işlevler çağırırsanız bir `CStdioFile`, karşılaşırsınız bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Kullanma hakkında daha fazla bilgi için `CStdioFile`, makalelerine bakın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile  
 Oluşturur ve başlatır bir `CStdioFile` nesnesi.  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parametreler  
 `pOpenStream`  
 C çalışma zamanı işlevine bir çağrı tarafından döndürülen dosya işaretçisini belirtir [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 `lpszFileName`  
 İstenen dosya yolu bir dizeyi belirtir. Yol, göreli veya mutlak olabilir.  
  
 `nOpenFlags`  
 Dosya oluşturma, dosya paylaşımı ve dosya erişim modları seçeneklerini belirtir. Bit düzeyinde OR kullanarak birden çok seçenek belirtebilirsiniz ( `|`) işleci.  
  
 Bir dosya erişim modu seçeneği gereklidir; Diğer modları isteğe bağlıdır. Bkz: [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) modu seçenekleri ve diğer bayraklar listesi. MFC sürüm 3.0 ve üstü, paylaşım bayrakları izin verilir.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Oluşturucu bir dosyaya eklemez `CStdioFile` nesnesi. Bu oluşturucuyu kullanırken kullanmalısınız `CStdioFile::Open` bir dosyayı açın ve kendisine eklemek için yöntemi `CStdioFile` nesnesi.  
  
 Tek parametre Oluşturucusu bir açık dosya akışı iliştirir `CStdioFile` nesnesi. İşaretçi değerler önceden tanımlanmış giriş/çıkış dosya işaretçileri izin `stdin`, `stdout`, veya `stderr`.  
  
 İki parametre Oluşturucusu oluşturur bir `CStdioFile` nesne ve karşılık gelen dosya ile belirtilen yol açar.  
  
 Geçirirseniz `NULL` ya da `pOpenStream` veya `lpszFileName`, Oluşturucusu oluşturur bir `CInvalidArgException*`.  
  
 Dosya açılan oluşturulamaz veya olursa Oluşturucusu oluşturur bir `CFileException*`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>  CStdioFile::m_pStream  
 `m_pStream` C çalışma zamanı işlevi tarafından döndürülen veri üyesi olduğu açık bir dosyayı işaretçisine `fopen`.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu **NULL** dosya hiç açılmış veya kapatıldı.  
  
##  <a name="open"></a>  CStdioFile::Open  
 Fazla Yüklendi. Açık varsayılan ile kullanılmak üzere tasarlanmıştır `CStdioFile` Oluşturucusu.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CAtlTransactionManager* pTM,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 İstenen dosyanın yolu olan bir dize. Yol, göreli veya mutlak olabilir.  
  
 `nOpenFlags`  
 Paylaşım ve erişim modu. Dosyayı açarken gerçekleştirilecek eylemi belirtir. Bit düzeyinde-OR kullanarak Seçenekleri birleştirebilirsiniz (&#124;) işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; modeCreate ve modeNoInherit modları isteğe bağlıdır.  
  
 `pError`  
 Bir işaretçi var olan bir dosya özel durumu nesneye başarısız bir işlemin durumunu alacak.  
  
 `pTM`  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="readstring"></a>  CStdioFile::ReadString  
 Bir sınırı kadar bir arabellek içine metin verileri okur `nMax`ilişkili dosyasından -1 karakter `CStdioFile` nesnesi.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsz`  
 Sonlandırılmış metin dizesini alacak kullanıcı tarafından sağlanan bir arabellek için bir işaretçi belirtir.  
  
 `nMax`  
 Sondaki boş karakter saymaz okumak için karakter üst sınırını belirtir.  
  
 `rString`  
 Bir başvuru bir `CString` işlevi döndüğünde dizeyi içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin verileri içeren arabellek için bir işaretçi. **NULL** dosya sonu herhangi bir veri; okumadan ulaştıysanız veya boolean ise, **FALSE** dosya sonu herhangi bir veri okumadan ulaştıysanız.  
  
### <a name="remarks"></a>Açıklamalar  
 Okuma ilk yeni satır karakteri tarafından durduruldu. Bu durumda, daha az ise `nMax`-1 karakter okuma, yeni satır karakteri arabellekte depolanır. Bir null karakter ('\0'), her iki durumda da eklenir.  
  
 [CFile::Read](../../mfc/reference/cfile-class.md#read) metin modu giriş, ancak değil sonlandırmak için bir satır başı satır besleme çifti üzerinde de kullanılabilir.  
  
> [!NOTE]
>  `CString` Bu işlev sürümünü kaldırır `'\n'` varsa; `LPTSTR` sürüm içermiyor.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>  CStdioFile::Seek  
 İşaretçinin daha önce açılmış bir dosyada yeniden konumlandırır.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Parametreler  
 `lOff`  
 İşaretçinin taşımak için bayt sayısı.  
  
 `nFrom`  
 İşaretçi taşıma modu. Aşağıdaki değerlerden biri olmalıdır:  
  
- `CFile::begin`: Taşıma dosya işaretçisini `lOff` bayt iletmek dosya baştan.  
  
- `CFile::current`: Taşıma dosya işaretçisini `lOff` dosyayı geçerli konumundan bayt.  
  
- `CFile::end`: Taşıma dosya işaretçisini `lOff` dosyasının sonuna baytlar. Unutmayın `lOff` gerekir olması mevcut arama negatif dosya; değerleri arama için dosya sonunun pozitif.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstenen konumu yasal, ise `Seek` dosyanın başından itibaren yeni bayt uzaklığı döndürür. Aksi takdirde, dönüş değeri tanımlanmamış ve `CFileException` nesnesi oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 `Seek` İşlevi izin verir. bir dosyanın içeriğini için rasgele erişim işaretçiyi taşıyarak belirtilen tutarı, mutlak veya göreli olarak. Hiçbir veri gerçekte arama sırasında okuyun. İstenen konumu dosya boyutundan büyük ise, bu konuma dosya uzunluğu uzatılır ve hiçbir özel durum.  
  
 Bir dosya açıldığında dosya işaretçisini uzaklığı 0, dosyasının başında konumlandırıldı.  
  
 Bu uygulaması, `Seek` çalışma zamanı kitaplığı (CRT) işlevine dayalı `fseek`. Kullanıma birkaç sınırları vardır `Seek` metin modunda açılmış akışları üzerinde. Daha fazla bilgi için bkz: [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `Seek` işaretçiyi 1000 bayt başından itibaren taşımak için `cfile` dosya. Unutmayın `Seek` sonradan çağırmanız gerekir böylece verileri okumaz [CStdioFile::ReadString](#readstring) veri okunamıyor.  
  
 [!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>  CStdioFile::WriteString  
 Verileri bir arabelleğinden ilişkili dosyaya yazar `CStdioFile` nesnesi.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpsz`  
 Sonlandırılmış bir dizeyi içeren bir arabellek için bir işaretçi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sondaki boş karakter ( `\0`) dosyasına yazılmaz. Bu yöntem satırbaşı karakterlerini Yazar `lpsz` dosyasına bir satır başı/satır besleme çifti olarak.  
  
 Bir dosyaya, kullanmak null ile sonlandırılmış olmayan veri yazmak istiyorsanız `CStdioFile::Write` veya [CFile::Write](../../mfc/reference/cfile-class.md#write).  
  
 Bu yöntem oluşturulur bir `CInvalidArgException*` belirtirseniz `NULL` için `lpsz` parametresi.  
  
 Bu yöntem oluşturulur bir `CFileException*` yanıt dosya sistemi hatalarını olarak.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [CNotSupportedException Sınıfı](../../mfc/reference/cnotsupportedexception-class.md)
