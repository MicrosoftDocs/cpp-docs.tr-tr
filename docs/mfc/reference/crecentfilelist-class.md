---
title: CRecentFileList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- CRecentFileList [MFC], CRecentFileList
- CRecentFileList [MFC], Add
- CRecentFileList [MFC], GetDisplayName
- CRecentFileList [MFC], GetSize
- CRecentFileList [MFC], ReadList
- CRecentFileList [MFC], Remove
- CRecentFileList [MFC], UpdateMenu
- CRecentFileList [MFC], WriteList
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 968c15b1382233dc166a174e4ef074033c76619c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crecentfilelist-class"></a>CRecentFileList sınıfı
En son kullanılan (MRU) dosya listesi denetimini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|Oluşturan bir `CRecentFileList` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|Bir dosyayı MRU dosya listesine ekler.|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|MRU filename menü görüntülenmesi için bir görünen ad sağlar.|  
|[CRecentFileList::GetSize](#getsize)|MRU dosya listesinde dosyalarının sayısını alır.|  
|[CRecentFileList::ReadList](#readlist)|MRU dosya listesi kayıt defterinden okur veya. INI dosyası.|  
|[CRecentFileList::Remove](#remove)|Bir dosya MRU dosya listesinden kaldırır.|  
|[CRecentFileList::UpdateMenu](#updatemenu)|MRU dosya listesi menü görüntüsünü güncelleştirir.|  
|[CRecentFileList::WriteList](#writelist)|MRU dosya listesi kayıt defterinden yazar veya. INI dosyası.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecentFileList::operator]](#operator_at)|Döndürür bir `CString` verilen konumda nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Dosyaları eklenen ya da MRU dosya listesinden silinir, dosya listesi okuma ya da kayıt defterine yazılır veya bir. INI dosyası ve MRU dosya listesini görüntüleme menüsünde güncelleştirilebilir.  
  
 MRU menü öğeleri hakkında daha fazla bilgi için bkz:  
  
-   Bilgi Bankası makalesi Q243751: nasıl yapılır: MFC uygulaması MRU menü öğeleri için komut işleyicileri ekleme  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CRecentFileList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxadv.h  
  
##  <a name="add"></a>CRecentFileList::Add  
 Bir dosyayı en son kullanılan (MRU) dosya listesine ekler.  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPathName`  
 Listeye eklenecek yol belirtir.  
  
 `lpszAppID`  
 Uygulama kullanıcısı Model kimliği için uygulama belirtir.  
  
 `pItem`  
 Listeye eklenecek Kabuk öğesi için bir işaretçi belirtir.  
  
 `pLink`  
 Kabuk listeye eklenecek bağlantı için bir işaretçi belirtir.  
  
 `pidl`  
 Yeni belgeleri klasörüne eklenmelidir Kabuk öğesi IDLIST belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya adı MRU listesinin üstüne eklenir. MRU listesinde dosya adı zaten varsa en çok taşınır.  
  
##  <a name="crecentfilelist"></a>CRecentFileList::CRecentFileList  
 Oluşturan bir `CRecentFileList` nesnesi.  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStart`  
 MRU (en son kullanılan) dosya listesi menü görüntüsünü numaralandırma için uzaklık.  
  
 `lpszSection`  
 Kayıt defteri veya uygulamanın bölümünün noktaları adı. Burada MRU dosya listesi okuma yazılmış ve/veya INI dosyası.  
  
 `lpszEntryFormat`  
 Kayıt defteri veya uygulamanın depolanan girişleri adları için kullanılacak biçim dizesi noktalarına. INI dosyası.  
  
 `nSize`  
 MRU dosya listesinde yer dosyaların maksimum sayısı.  
  
 `nMaxDispLen`  
 Uzunluk üst sınırını karakter, bir dosya adı MRU dosya listesinde menü görüntüsü için kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için biçim dizesi işaret `lpszEntryFormat` "% her MRU öğenin dizini değiştirme için kullanılacak olan d", içermelidir. Örneğin, biçim dizesi ise `"file%d"` girişleri adlı sonra `file0`, `file1`ve benzeri.  
  
##  <a name="getdisplayname"></a>CRecentFileList::GetDisplayName  
 MRU dosya listesinde dosyanın MRU Listesi menü görünümünü kullanmak için görünen adını alır.  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `strName`  
 MRU Dosya menüsü listesinde gösterilecek adı olan dosyasının tam yolu.  
  
 `nIndex`  
 MRU dosya listesi dosyasında sıfır tabanlı dizini.  
  
 *lpszCurDir*  
 Geçerli dizin bulunduran dize.  
  
 *nCurDir*  
 Geçerli dizin dizesi uzunluğu.  
  
 `bAtLeastName`  
 En büyük görüntü uzunluğu aşması durumunda bile sıfır olmayan, temel dosyanın adını döndürülmelidir olduğunu, gösterir (olarak geçirilen `nMaxDispLen` parametresi `CRecentFileList` Oluşturucusu).  
  
### <a name="return-value"></a>Dönüş Değeri  
 **YANLIŞ** olup olmadığını bir dosya adı belirtilen dizinden en son kullanılan (MRU) dosya listesinde.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli dizinde dosyasıysa işlevi directory görüntülenmesini devre dışı bırakır. Dosya adı çok uzun olması durumunda dizin ve uzantı kaldırılır. Dosya adı hala çok uzun olduğunda görünen adı boş bir dize olarak sürece ayarlandığı `bAtLeastName` sıfır olmayan bir değer değil.  
  
##  <a name="getsize"></a>CRecentFileList::GetSize  
 MRU dosya listesinde dosyalarının sayısını alır.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dosya sayısı, en son (MRU) dosya listesi kullanılır.  
  
##  <a name="operator_at"></a>CRecentFileList::operator]  
 Aşırı yüklenmiş alt simge ( `[]`) operatörü döndürür tek bir `CString` içindeki sıfır tabanlı dizin tarafından belirtilen `nIndex`.  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Sıfır tabanlı dizini bir `CString` kümesinde `CString`s.  
  
##  <a name="readlist"></a>CRecentFileList::ReadList  
 En son kullanılan (MRU) dosya listesi kayıt defterinden ya da uygulamanın okur. INI dosyası.  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>CRecentFileList::Remove  
 Bir dosya MRU dosya listesinden kaldırır.  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dosyanın en son kullanılan (MRU) dosya listesinden kaldırılacak sıfır tabanlı dizini.  
  
##  <a name="updatemenu"></a>CRecentFileList::UpdateMenu  
 MRU dosya listesi menü görüntüsünü güncelleştirir.  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi [Ccmduı](../../mfc/reference/ccmdui-class.md) en son kullanılan (MRU) dosya listesi menüsü nesne.  
  
##  <a name="writelist"></a>CRecentFileList::WriteList  
 En son kayıt defteri ya da uygulamanın (MRU) dosya listesi kullanılan yazar. INI dosyası.  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



