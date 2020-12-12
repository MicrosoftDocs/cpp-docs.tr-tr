---
description: 'Daha fazla bilgi edinin: CStdioFile sınıfı'
title: CStdioFile sınıfı
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 9eda9054026635fd986cc5555d6f3260422438d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318630"
---
# <a name="cstdiofile-class"></a>CStdioFile sınıfı

Çalışma zamanı işlevi [fopen](../../c-runtime-library/reference/fopen-wfopen.md)tarafından açılan bir C çalışma zamanı akış dosyasını temsil eder.

## <a name="syntax"></a>Syntax

```
class CStdioFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile:: CStdioFile](#cstdiofile)|`CStdioFile`Bir yol veya dosya işaretçisinden bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile:: Open](#open)|Fazla Yüklendi. Open varsayılan oluşturucuyla kullanılmak üzere tasarlanmıştır `CStdioFile` (geçersiz kılmalar [CFile:: Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile:: ReadString](#readstring)|Tek satırlık bir metin okur.|
|[CStdioFile:: Seek](#seek)|Geçerli dosya işaretçisini konumlandırır.|
|[CStdioFile:: WriteString](#writestring)|Tek satırlık bir metin yazar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile:: m_pStream](#m_pstream)|Açık dosya için bir işaretçi içerir.|

## <a name="remarks"></a>Açıklamalar

Akış dosyaları arabelleğe alınır ve herhangi bir metin modunda (varsayılan) veya ikili modda açılabilir.

Metin modu, satır başı satır besleme çiftleri için özel işlem sağlar. Bir metin modu nesnesine bir satır besleme (yeni satır) karakteri (0x0A) yazdığınızda `CStdioFile` , bayt çifti (0x0D, 0x0A) dosyaya gönderilir. Okurken, bayt çifti (0x0D, 0x0A) tek bir 0x0A bayta çevrilir.

[CFile](../../mfc/reference/cfile-class.md) işlevleri [yineleniyor](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange)ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) için desteklenmez `CStdioFile` .

Bu işlevleri bir üzerinde çağırırsanız `CStdioFile` , bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)alacaksınız.

Kullanma hakkında daha fazla bilgi için `CStdioFile` bkz. [MFC 'Deki makale dosyaları](../../mfc/files-in-mfc.md) ve *çalışma zamanı kitaplık başvurusunda* [Dosya işleme](../../c-runtime-library/file-handling.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cstdiofilecstdiofile"></a><a name="cstdiofile"></a> CStdioFile:: CStdioFile

Bir nesnesi oluşturur ve başlatır `CStdioFile` .

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

*pOpenStream*<br/>
C çalışma zamanı işlevi [fopen](../../c-runtime-library/reference/fopen-wfopen.md)çağrısı tarafından döndürülen dosya işaretçisini belirtir.

*lpszFileName*<br/>
İstenen dosyanın yolu olan bir dize belirtir. Yol göreli veya mutlak olabilir.

*nOpenFlags*<br/>
Dosya oluşturma, dosya paylaşımı ve dosya erişim modları için seçenekleri belirtir. Bit düzeyinde OR () işlecini kullanarak birden çok seçenek belirleyebilirsiniz **|** .

Bir dosya erişim modu seçeneği gereklidir; Diğer modlar isteğe bağlıdır. Mod seçeneklerinin ve diğer bayrakların listesi için bkz. [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile) . MFC sürüm 3,0 ve üzeri sürümlerde, paylaşım bayraklarına izin verilir.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu nesnesine bir dosya eklemez `CStdioFile` . Bu oluşturucuyu kullanırken, `CStdioFile::Open` bir dosyayı açmak ve nesneye iliştirmek için yöntemini kullanmanız gerekir `CStdioFile` .

Tek parametreli Oluşturucu, nesnesine bir açık dosya akışı iliştirir `CStdioFile` . İzin verilen işaretçi değerleri, önceden tanımlanmış giriş/çıkış dosyası işaretçilerini *STDIN*, *stdout* veya *stderr* içerir.

İki parametreli Oluşturucu bir `CStdioFile` nesne oluşturur ve ilgili dosyayı verilen yola açar.

Ya *pOpenStream* veya *lpszFileName* için null geçirirseniz, Oluşturucu bir oluşturur `CInvalidArgException*` .

Dosya açılamadığı veya oluşturulamadığı takdirde, Oluşturucu bir oluşturur `CFileException*` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

## <a name="cstdiofilem_pstream"></a><a name="m_pstream"></a> CStdioFile:: m_pStream

`m_pStream`Veri üyesi, C çalışma zamanı işlevi tarafından döndürülen açık bir dosyanın işaretçisidir `fopen` .

```
FILE* m_pStream;
```

### <a name="remarks"></a>Açıklamalar

Dosya açılmadıysa veya kapatılmışsa NULL olur.

## <a name="cstdiofileopen"></a><a name="open"></a> CStdioFile:: Open

Fazla Yüklendi. Open, varsayılan oluşturucuyla kullanılmak üzere tasarlanmıştır `CStdioFile` .

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

*lpszFileName*<br/>
İstenen dosyanın yolu olan bir dize. Yol göreli veya mutlak olabilir.

*nOpenFlags*<br/>
Paylaşım ve erişim modu. Dosya açılırken gerçekleştirilecek eylemi belirtir. Bit düzeyinde OR (&#124;) işlecini kullanarak seçenekleri birleştirebilirsiniz. Bir erişim izni ve bir paylaşma seçeneği gereklidir; modeCreate ve Monominal Inherit modları isteğe bağlıdır.

*pError*<br/>
Hatalı bir işlemin durumunu alacak olan, var olan bir dosya özel durum nesnesine yönelik bir işaretçi.

*pTM*<br/>
Bir nesne işaretçisi `CAtlTransactionManager` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cstdiofilereadstring"></a><a name="readstring"></a> CStdioFile:: ReadString

Metin verilerini, nesnesiyle ilişkili dosyadan *NMAX*-1 karakter sınırına kadar bir arabelleğe okur `CStdioFile` .

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null ile sonlandırılmış bir metin dizesi alacak Kullanıcı tarafından sağlanan arabellek için bir işaretçi belirtir.

*Ngünde en çok*<br/>
Sonlandıran null karakteri saymayan okunacak en fazla karakter sayısını belirtir.

*rString*<br/>
`CString`İşlevin döndürdüğü dizeyi içeren bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Metin verisini içeren arabelleğin işaretçisi. Herhangi bir veri okunmadan dosya sonu ulaşılırsa NULL; ya da Boolean ise, herhangi bir veri okunmadan dosya sonu ulaşılırsa FALSE 'TUR.

### <a name="remarks"></a>Açıklamalar

Okuma ilk yeni satır karakteri tarafından durdurulur. Bu durumda, *NMAX*-1 ' den az karakter okunıyorsa, bir yeni satır karakteri arabellekte depolanır. Her iki durumda da null karakter (' \ 0 ') eklenir.

[CFile:: Read](../../mfc/reference/cfile-class.md#read) , metin modu girişi için de kullanılabilir, ancak bir satır başı satır akış çiftinde sonlanmaz.

> [!NOTE]
> `CString`Bu işlevin sürümü `'\n'` varsa KALDıRıR; LPTSTR sürümü desteklemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

## <a name="cstdiofileseek"></a><a name="seek"></a> CStdioFile:: Seek

Daha önce açılmış bir dosyadaki işaretçiyi konumlandırır.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
İşaretçiyi taşıyacağınız bayt sayısı.

*Ngüncelleştirmelerini*<br/>
İşaretçi taşıma modu. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin`: *Dosya işaretçisini dosyanın* başlangıcından ileri doğru taşı.

- `CFile::current`: Dosya işaretçisini dosyadaki geçerli konumdan *kapatır* .

- `CFile::end`: Dosya işaretçisini dosyanın sonundan *kapatır* . *LOff* 'ın mevcut dosyaya arama yapmak için negatif olması gerektiğini unutmayın; pozitif değerler dosyanın sonundan daha sonra aranacaktır.

### <a name="return-value"></a>Dönüş Değeri

İstenen konum geçerli ise, `Seek` dosyanın başından başlayarak yeni bayt sapmasını döndürür. Aksi takdirde, dönüş değeri tanımsızdır ve bir `CFileException` nesne oluşturulur.

### <a name="remarks"></a>Açıklamalar

`Seek`İşlevi, işaretçiyi belirtilen miktarda, kesinlikle veya görece taşıyarak bir dosyanın içeriğine rastgele erişime izin verir. Arama sırasında hiç veri okunmamıştır. İstenen konum dosyanın boyutundan büyükse, dosya uzunluğu bu konuma genişletilir ve hiçbir özel durum oluşturulmaz.

Dosya açıldığında dosya işaretçisi, dosyanın başına 0 uzaklığında konumlandırılır.

Bu uygulama, `Seek` Run-Time kitaplığı (CRT) işlevini temel alır `fseek` . `Seek`Metin modunda açılan akışlarda kullanımı için birkaç sınır vardır. Daha fazla bilgi için bkz. [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, `Seek` 1000 baytlık işaretçiyi dosyanın başından taşımak için nasıl kullanılacağını gösterir `cfile` . `Seek`Verileri okumadığını unutmayın. bu nedenle, verileri okumak için daha sonra [CStdioFile:: ReadString](#readstring) ' i çağırmanız gerekir.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

## <a name="cstdiofilewritestring"></a><a name="writestring"></a> CStdioFile:: WriteString

Bir arabellekteki verileri nesneyle ilişkili dosyaya yazar `CStdioFile` .

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null ile sonlandırılmış bir dize içeren bir arabelleğin işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı null karakteri ( `\0` ) dosyaya yazılmadı. Bu yöntem, *lpsz* ' de satır başı satır besleme çifti olarak bir satır başı karakteri yazar.

Null ile Sonlandırılmamış verileri bir dosyaya yazmak istiyorsanız `CStdioFile::Write` veya [CFile:: Write](../../mfc/reference/cfile-class.md#write)kullanın.

Bu yöntem `CInvalidArgException*` , *lpsz* parametresi için null belirtirseniz bir oluşturur.

Bu yöntem `CFileException*` , dosya sistemi hatalarına yanıt olarak bir yanıt verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CFile::D yukarı](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile:: LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile:: UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException sınıfı](../../mfc/reference/cnotsupportedexception-class.md)
