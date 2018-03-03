---
title: "Ftmbase::unmarshalınterface metodu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3710e84a9f7680b56f461029f279a659a5c14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface Metodu
Yeni oluşturulan bir proxy başlatır ve proxy için bir arabirim işaretçisi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStm`  
 Arabirim işaretçisi iptal olmasını olduğu akış işaretçi.  
  
 `riid`  
 İptal olmasını arabirimi tanıtıcısı başvuru.  
  
 `ppv`  
 Bu işlem tamamlandığında, içinde istenen arabirim işaretçisi alan işaretçi değişkenin adresini `riid`. Bu işlem başarılı olursa *`ppv` iptal olmasını arabiriminin istenen arabirim işaretçisi içerir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_NOINTERFACE veya E_FAIL.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)