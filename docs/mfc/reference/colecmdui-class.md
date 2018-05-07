---
title: COleCmdUI sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6195735c25bb188449638750f6100869a44f082
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="colecmdui-class"></a>COleCmdUI sınıfı
Kullanıcı arabirimi nesneleri durumunu güncelleştirmek MFC için bir yöntem ile ilgili uygulayan `IOleCommandTarget`-uygulamanızın özelliklerini güdümlü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Oluşturan bir `COleCmdUI` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Ayarlar veya etkinleştirme komutu bayrağını temizler.|  
|[COleCmdUI::SetCheck](#setcheck)|Açık/kapalı iki durumlu durumunu ayarlar komutu.|  
|[COleCmdUI::SetText](#settext)|Bir komut bir metin adı ya da durum dize döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı uygulama, MFC işlemleri menü görüntülediğinde DocObjects için etkinleştirilmemiş bir uygulamada **UPDATE_COMMAND_UI** bildirimler. Her bir bildirim verilen bir [Ccmduı](../../mfc/reference/ccmdui-class.md) belirli bir komut durumunu yansıtacak biçimde yönetilebilmesini nesnesi. Ancak, uygulamanız için DocObjects etkinleştirildiğinde, MFC işler **UPDATE_OLE_COMMAND_UI** bildirimleri ve atar `COleCmdUI` nesneleri.  
  
 `COleCmdUI` kapsayıcısının kullanıcı arabiriminde (örneğin, dosya yeni, Aç, yazdırma vb.) kaynaklanan komutları almak üzere DocObject verir ve DocObject'ın kullanıcı arabiriminde kaynaklanan komutları almak için bir kapsayıcı sağlar. Ancak `IDispatch` aynı komutları gönderilmesi için kullanılabilecek `IOleCommandTarget` sorgulamak ve komutları, bağımsız değişken olmadan genellikle standart kümesi kullanır ve hiçbir tür bilgileri dahil olduğundan yürütmek için daha basit bir yol sağlar. `COleCmdUI` etkinleştirme, güncelleştirme ve diğer DocObject kullanıcı arabirimi komutları özelliklerini ayarlamak için kullanılabilir. Komut çağırma istediğinizde, çağrı [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 DocObjects hakkında daha fazla bilgi için bkz: [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). Ayrıca bkz. [Internet ilk adımlar: etkin belgeler](../../mfc/active-documents-on-the-internet.md) ve [etkin belgeler](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Ccmduı](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocobj.h  
  
##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI  
 Oluşturan bir `COleCmdUI` belirli kullanıcı arabirimi komutla ilişkili nesne.  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 `rgCmds`  
 Verilen GUID ile ilişkili desteklenen komutlar listesi. **OLECMD** yapısı komutu bayraklarıyla komutları ilişkilendirir.  
  
 *cCmds*  
 Komutlarda sayısı `rgCmds`.  
  
 `pGroup`  
 Bir işaretçi komutları kümesini tanımlayan bir GUID.  
  
### <a name="remarks"></a>Açıklamalar  
 `COleCmdUI` Nesnesi menü öğelerini veya denetim çubuğu düğmelerini gibi DocObject kullanıcı arabirimi nesnelerini güncelleştirme için programa dayalı bir arabirim sağlar. Kullanıcı arabirimi nesneleri etkin, devre dışı, kullanıma ve/veya aracılığıyla temizlenmiş `COleCmdUI` nesnesi.  
  
##  <a name="enable"></a>  COleCmdUI::Enable  
 Komut bayrağı ayarlamak için bu işlevi çağırmak `COleCmdUI` nesnesini **OLECOMDF_ENABLED**, kullanılabilir ve etkin, komut arabirimi söyleyen ya da komut bayrağını temizleyin.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Parametreler  
 `bOn`  
 Komutu ile ilişkili olup olmadığını gösteren `COleCmdUI` nesne etkinleştirilecek veya devre dışı. NonZero komutu sağlar; 0 komutu devre dışı bırakır.  
  
##  <a name="setcheck"></a>  COleCmdUI::SetCheck  
 Açık/kapalı iki durumlu durumunu ayarlamak için bu işlevi çağırmak komutu.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCheck`  
 Açık/kapalı iki durumlu ayarlamak için durumu belirleme bir değer komutu. Değerler şunlardır:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**1**|Komut göre ayarlar.|  
|**2**|Komut için belirsiz ayarlar; Bu komutun özniteliği hem şirket hem de ilgili seçim Devletler'de devre dışı olduğundan durumu belirlenemiyor.|  
|Başka bir değer|Komutu, OFF olarak ayarlar.|  
  
##  <a name="settext"></a>  COleCmdUI::SetText  
 Bir komut için bir metin adı ya da durum dize döndürmek için bu işlevini çağırın.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszText`  
 Komutu ile kullanılacak metni için bir işaretçi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



