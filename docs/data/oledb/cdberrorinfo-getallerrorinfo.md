---
title: "Cdberrorınfo::getallerrorınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs: C++
helpviewer_keywords: GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46e233800f814b39e4e14f0b357c381a3e71311e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
Bir hata kaydında bulunan hata bilgilerinin tüm türleri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ulRecordNum*  
 [in] Hata bilgilerini döndürmek kaydı sıfır tabanlı sayısı.  
  
 `lcid`  
 [in] Yerel ayar kimliği döndürülen hata bilgileri için.  
  
 `pbstrDescription`  
 [out] Bir metin açıklama hata ya da yerel desteklenmiyorsa NULL işaretçi. Açıklamalar bakın.  
  
 `pbstrSource`  
 [out] Hatayı oluşturan bileşen adını içeren bir dize için bir işaretçi.  
  
 `pguid`  
 [out] Bir işaretçi hata tanımlı arabirimi GUID.  
  
 *pdwHelpContext*  
 [out] Hata için Yardım içerik kimliği için bir işaretçi.  
  
 *pbstrHelpFile*  
 [out] Hatayı açıklayan Yardım dosyasının yolunu içeren bir dize için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK`başarılı olursa. Bkz: [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) içinde *OLE DB Programcının Başvurusu* diğer dönüş değerleri için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="remarks"></a>Açıklamalar  
 Çıkış değeri `pbstrDescription` yerel desteklenmiyorsa ya da aşağıdaki koşulların her ikisi de doğruysa, değeri NULL olarak ayarlar arama IErrorInfo::GetDescription tarafından dahili olarak elde edilir:  
  
1.  değeri `lcid` ABD değil İngilizce ve  
  
2.  değeri `lcid` olan GetUserDefaultLCID tarafından döndürülen değer eşit değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDBErrorInfo Sınıfı](../../data/oledb/cdberrorinfo-class.md)