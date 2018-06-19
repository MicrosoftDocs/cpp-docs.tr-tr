---
title: OLE denetimlerini kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e51e4c425d3d16b57a2b1ce0d4fc2f585dc505d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378063"
---
# <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme
OLE denetimleri diğer OLE sunucu nesneleri gibi OLE kullanan diğer uygulamalar tarafından erişilebilir. Bu denetimin tür kitaplığı ve sınıf kaydederek sağlanır.  
  
 Aşağıdaki işlevleri ekleyip denetimin sınıf, özellik sayfaları ve tür kitaplığı Windows kayıt veritabanı'nda izin ver:  
  
### <a name="registering-ole-controls"></a>OLE Denetimlerini Kaydetme  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Denetimin sınıf kayıt veritabanına ekler.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Bir denetim özellik sayfası kayıt veritabanına ekler.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Denetimin tür kitaplığı kaydı veritabanına ekler.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Bir denetim sınıf veya özellik sayfasında sınıfı kayıt veritabanından kaldırır.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Denetimin tür kitaplığı kaydı veritabanından kaldırır.|  
  
 `AfxOleRegisterTypeLib` genellikle bir denetim DLL'nin uygulamasında olarak da adlandırılır `DllRegisterServer`. Benzer şekilde, `AfxOleUnregisterTypeLib` tarafından çağrılır `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, ve `AfxOleUnregisterClass` genellikle denir `UpdateRegistry` bir denetimin sınıf Fabrika veya özellik sayfasının üye işlevi.  
  
##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass  
 Denetim sınıfı Windows kayıt veritabanı ile kaydeder.  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Denetim sınıfı ile ilişkili modülü örneği tanıtıcısı.  
  
 `clsid`  
 Denetimin benzersiz sınıf kimliği.  
  
 `pszProgID`  
 Denetimin benzersiz program kimliği.  
  
 `idTypeName`  
 Denetim için bir kullanıcı tarafından okunabilir tür adını içeren dize kaynak kimliği.  
  
 *idBitmap*  
 Bir araç veya palet OLE denetimindeki temsil etmek için kullanılan bit eşlem kaynak kimliği.  
  
 `nRegFlags`  
 Bir veya daha fazla aşağıdaki bayraklar içerir:  
  
- `afxRegInsertable` OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesi denetimi sağlar.  
  
- `afxRegApartmentThreading` İş parçacığı modelini ThreadingModel için kayıt defterindeki ayarlar Grup =.  
  
- `afxRegFreeThreading` İş parçacığı modelini ThreadingModel için kayıt defterindeki ayarlar serbest =.  
  
     İki bayrak birleştirebilirsiniz `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel ayarlamak için her ikisini de =. Bkz: [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) modeli kaydı iş parçacığı oluşturma hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
> [!NOTE]
>  MFC 4.2 önce MFC sürümlerde `int` `nRegFlags` parametresi bir **BOOL** parametresi *bInsertable*, izin verilen veya izin verilmeyen nesne Ekle iletişim kutusundan eklenecek denetimi bir kutu.  
  
 *dwMiscStatus*  
 Bir veya daha fazla aşağıdaki durumu bayrakları içerir (bayrakları açıklaması için bkz: **OLEMISC** Windows SDK'sındaki numaralandırması):  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   OLEMISC_ACTIVATEWHENVISIBLE  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 Denetim sınıfı benzersiz kimliği.  
  
 `wVerMajor`  
 Denetim sınıfı ana sürüm numarası.  
  
 `wVerMinor`  
 Denetim sınıfı ikincil sürüm numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim sınıfı kaydolduysanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetim kullanan OLE kapsayıcıları tarafından kullanılmak üzere denetim sağlar. `AfxOleRegisterControlClass` denetimin adı ve konumu sistem üzerindeki kayıt defterini güncelleştirir ve ayrıca kayıt defterinde denetimi destekleyen iş parçacığı modelini ayarlar. Daha fazla bilgi için bkz: [Teknik Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartman modeli iş parçacığı içinde OLE denetimleri," ve [ilgili işlemler ve iş parçacıkları](http://msdn.microsoft.com/library/windows/desktop/ms681917) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 Yukarıdaki örnekte gösterilmiştir nasıl `AfxOleRegisterControlClass` bayrağı belirten gösterge çağrılır ve grup için bayrağı model bölümleri birlikte altıncı parametrenin oluşturmak için:  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Denetim etkin kapsayıcıları için Nesne Ekle iletişim kutusunda görünür ve apartman modeli algılayan olacaktır. Böylece bir grup denetiminde statik verilere erişilirken olsa da, Zamanlayıcı tarafından tamamlandıktan ve kullanarak aynı sınıfın başka bir örneğini başlatır önce devre dışı değil apartman modeli algılayan denetimleri kilitlediği, korumalı verileri bu statik sınıf emin olmalısınız aynı statik verileri. Statik veri herhangi bir erişimin kritik bölüm kodla çevrelenen.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Özellik sayfası sınıfı Windows kayıt veritabanı ile kaydeder.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Özellik sayfası sınıfıyla ilişkili modülü örneği tanıtıcısı.  
  
 `clsid`  
 Özellik sayfası benzersiz sınıf kimliği.  
  
 `idTypeName`  
 Özellik sayfası için bir kullanıcı tarafından okunabilir ad içeren dize kaynak kimliği.  
  
 `nRegFlags`  
 Bayrak içerebilir:  
  
- `afxRegApartmentThreading` İş parçacığı modelini ThreadingModel için kayıt defterindeki ayarlar Grup =.  
  
> [!NOTE]
>  MFC 4.2 önce MFC sürümlerde `int` `nRegFlags` parametresi kullanılabilir değildi. Ayrıca `afxRegInsertable` bayrağı özellik sayfaları için geçerli bir seçenek değil ve bu ayarlanırsa bir ASSERT MFC'de neden olur  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim sınıfı kaydolduysanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetim kullanan OLE kapsayıcıları tarafından kullanılacak özellik sayfası sağlar. `AfxOleRegisterPropertyPageClass` özellik sayfası adını ve konumunu sistemdeki ile kayıt defterini güncelleştirir ve ayrıca kayıt defterinde denetimi destekleyen iş parçacığı modelini ayarlar. Daha fazla bilgi için bkz: [Teknik Not 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartman modeli iş parçacığı içinde OLE denetimleri," ve [ilgili işlemler ve iş parçacıkları](http://msdn.microsoft.com/library/windows/desktop/ms681917) Windows SDK'sındaki.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Tür kitaplığı Windows kayıt veritabanı ile kaydeder ve OLE-denetim kullanan diğer kapsayıcıları tarafından kullanılması tür kitaplığı sağlar.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Parametreler  
 `hInstance`  
 Tür kitaplığı ile ilişkili uygulamayı örneği tanıtıcısı.  
  
 *tlid*  
 Tür kitaplığı benzersiz kimliği.  
  
 *pszFileName*  
 Yerelleştirilmiş tür kitaplığı için isteğe bağlı filename noktaları (. Denetim için TLB) dosyası.  
  
 *pszHelpDir*  
 Tür kitaplığı için Yardım dosyasına bulunabileceği dizinin adı. Varsa **NULL**, Yardım dosyasının tür kitaplığı olarak aynı dizinde olduğu varsayılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tür kitaplığı kaydolduysanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tür kitaplığı adını ve konumunu sistemdeki ile kayıt defterini güncelleştirir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Denetim veya özellik sayfasında sınıf girdisi Windows kayıt veritabanından kaldırır.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 Denetim veya özellik sayfasında benzersiz sınıf kimliği.  
  
 `pszProgID`  
 Denetim veya özellik sayfasında benzersiz program kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim veya özellik sayfasında sınıfı kaydı başarıyla silindi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Tür kitaplığı giriş Windows kayıt veritabanından kaldırmak için bu işlevini çağırın.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Parametreler  
 `tlID`  
 Tür kitaplığı benzersiz kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tür kitaplığı kaydı başarıyla silindi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
