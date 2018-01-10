---
title: "COleDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
dev_langs: C++
helpviewer_keywords: COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae60b9e5a0d2e79d2bf6d9cc06eebfa9df0c6e23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledialog-class"></a>COleDialog sınıfı
İletişim kutularına ortak işlevsellik için OLE sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDialog::GetLastError](#getlasterror)|İletişim kutusu tarafından döndürülen hata kodu alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Microsoft Foundation Class Kitaplığı türetilmiş çeşitli sınıflar sağlar `COleDialog`:  
  
- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)  
  
- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)  
  
- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)  
  
- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)  
  
- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)  
  
- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)  
  
- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)  
  
- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `COleDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="getlasterror"></a>COleDialog::GetLastError  
 Çağrı `GetLastError` ek hata bilgileri almak için üye işlevini zaman `DoModal` döndürür **IDABORT**.  
  
```  
UINT GetLastError() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından döndürülen hata kodlarını `GetLastError` belirli iletişim kutusunda görüntülenen bağlıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: `DoModal` özel hata iletileri hakkında bilgi için türetilmiş sınıflardaki üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommonDialog sınıfı](../../mfc/reference/ccommondialog-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



