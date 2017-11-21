---
title: CBulkRowset::MoveToBookmark | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs: C++
helpviewer_keywords: MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1671a0b03b3dbc637d83fd1e0f5125bc4abb1f1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Yer işareti veya belirtilen kayma satırındaki tarafından işaretlenen satırı getirir (`lSkip`) bu yer işaretinin gelen.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `bookmark`  
 [in] Veri getirmek istediğiniz konumu işaretleme yer işareti.  
  
 `lSkip`  
 [in] Yer işareti satırları hedef satır numarası sayısı. Varsa `lSkip` sıfır getirilen ilk satırın işaretli satırıdır. Varsa `lSkip` 1, ilk satırın getirilen satır sonra işaretli satırıdır. Varsa `lSkip` -1 ' dir getirilen ilk satır işaretli satır önce satırıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bkz: ['yı](https://msdn.microsoft.com/en-us/library/ms716988.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CBulkRowset sınıfı](../../data/oledb/cbulkrowset-class.md)