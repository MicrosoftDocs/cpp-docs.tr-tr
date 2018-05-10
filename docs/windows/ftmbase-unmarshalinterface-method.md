---
title: Ftmbase::unmarshalınterface metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 964ce5cc33b51c54446874522317814279cdd960
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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