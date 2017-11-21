---
title: CBookmark::CBookmark | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class, constructor
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0b38e91830157621835ad12edaeb37c24b8e11d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cbookmarkcbookmark"></a>CBookmark::CBookmark
Oluşturucu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nSize`  
 [in] Yer işareti arabelleğinin bayt cinsinden boyutu.  
  
## <a name="remarks"></a>Açıklamalar  
 Arabellek ilk işlev ayarlar **NULL** ve 0 arabellek boyutu. Arabellek boyutu ikinci işlev ayarlar `nSize`ve bir bayt dizisi arabelleğe `nSize` bayt sayısı.  
  
> [!NOTE]
>  Bu işlev yalnızca kullanılabilir **CBookmark\<0 >**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CBookmark sınıfı](../../data/oledb/cbookmark-class.md)