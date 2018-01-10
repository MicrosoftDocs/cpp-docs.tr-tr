---
title: "CDockState sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs: C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6669f5a2b54c376e545b1ba6b9227d6137726256
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdockstate-class"></a>CDockState sınıfı
Seri hale getirilmiş bir `CObject` yükler, kaldırır ya da bir veya daha fazla yerleştirme denetim durumunu temizler sınıfı çubuklarını kalıcı bellek (dosya).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Yerleştirme durum bilgilerini temizler.|  
|[CDockState::GetVersion](#getversion)|Depolanan sürüm numarasını alır çubuk durumu.|  
|[CDockState::LoadState](#loadstate)|Durum bilgilerini kayıt defterinden alır veya. INI dosyası.|  
|[CDockState::SaveState](#savestate)|Durum bilgileri kayıt defteri veya INI dosyası kaydeder.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|İşaretçileri saklı dizisi her denetim çubuğu için bir giriş durum bilgileriyle yerleştirme.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yerleştirme durumu boyutunu ve konumunu çubuğu ve desteklemediğini yerleşik içerir. Ne zaman alınırken saklı izin ver yerleştirme durumu, `CDockState` çubuğunun denetler konumu ve çubuğu geçerli ekran ayarlarla görünür değilse `CDockState` çubuğunun ölçeklendirir böylece görünür getirin. Ana amacı `CDockState` bir dizi denetim çubukları tüm durumunu tutacak ve kaydedilmesi bu duruma izin vermek için ve ya da kayıt defterindeki, uygulama yüklenir. INI dosyası veya ikili biçimde bir parçası olarak bir `CArchive` nesnenin içeriği.  
  
 Çubuğunun çubuk, araç, durum çubuğu ya da iletişim çubuğu dahil olmak üzere herhangi bir dockable denetimi olabilir. `CDockState`nesneleri yazılmış ve okuma için veya bir dosyadan bir `CArchive` nesnesi.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) tüm çerçeve pencere durumu bilgilerini alır `CControlBar` nesneleri ve içine yerleştirir `CDockState` nesnesi. Ardından içeriğini yazmak `CDockState` depolama ile nesnesine [serileştirme](../../mfc/reference/cobject-class.md#serialize) veya [CDockState::SaveState](#savestate). Daha sonra çerçeve penceresindeki denetim çubukları durumunu geri yüklemek istiyorsanız, durumuyla yükleyebilir `Serialize` veya [CDockState::LoadState](#loadstate), ardından [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) kaydedilen uygulamak için çerçeve pencere denetim çubukları durumuna.  
  
 Denetim çubukları yerleştirme daha fazla bilgi için makalelerine bakın [denetim çubukları](../../mfc/control-bars.md), [araç çubukları: yerleşen ve kayan](../../mfc/docking-and-floating-toolbars.md), ve [çerçeve pencereleri](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxadv.h  
  
##  <a name="clear"></a>CDockState::Clear  
 İçinde depolanan tüm takma bilgilerini temizlemek için bu işlevi çağırmak `CDockState` nesnesi.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, yalnızca çubuğu ya da değildir, çubuğunun boyutunu ve konumunu yerleştirilmiş olup olmadığını ve görünür olup olmadığını içerir.  
  
##  <a name="getversion"></a>CDockState::GetVersion  
 Depolanan sürüm numarasını almak için bu işlevi çağırmak çubuk durumu.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 1 IF saklı çubuğu bilgidir sürümden geçerli durumu; çubuğu 2 IF saklı çubuğu bilgi aynıdır geçerli çubuk durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni kalıcı özellikleri ekleyin ve yine algılayıp çubuğu önceki bir sürümü tarafından oluşturulmuş kalıcı durumunu yüklemek için yeniden düzenlenen çubuğu sürüm desteği sağlar.  
  
##  <a name="loadstate"></a>CDockState::LoadState  
 Kayıt defterinden durum bilgilerini almak için bu işlevi çağırmak veya. INI dosyası.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszProfileName`  
 Noktaları bir null teminated dizeye başlatma dosyası ya da durum bilgilerini depolandığı Windows kayıt defteri anahtarında bölümün adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Profil adı uygulamanın bölümüdür. INI dosyası veya çubukları durum bilgilerini içeren kayıt defteri. Denetim çubuğu durum bilgilerini kayıt defterine kaydedebilirsiniz veya. INI dosyası ile `SaveState`.  
  
##  <a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 A `CPtrArray` durum bilgilerini kaydetti her denetim çubuğu depolanan denetim çubuğu bilgilerini işaretçiler bir dizi nesnesi `CDockState` nesnesi.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>CDockState::SaveState  
 Durum bilgilerini kayıt defterine kaydetmek için bu işlevi çağırmak veya. INI dosyası.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszProfileName`  
 Noktaları bir null teminated dizeye başlatma dosyası ya da durum bilgilerini depolandığı Windows kayıt defteri anahtarında bölümün adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Profil adı uygulamanın bölümüdür. INI dosyası veya kayıt içeren denetim çubuğu durum bilgileri. `SaveState`Ayrıca geçerli ekran boyutu kaydeder. Denetim çubuğu bilgileri kayıt defterinden alabilir veya. INI dosyası ile `LoadState`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

