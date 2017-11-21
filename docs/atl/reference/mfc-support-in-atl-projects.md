---
title: "ATL projeleri MFC desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.atl.addmfc
dev_langs: C++
helpviewer_keywords: ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0217c62ff207ad706dbcb1cd172e878c2b96daee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-support-in-atl-projects"></a>ATL projeleri MFC desteği
Seçerseniz **destek MFC** uygulaması MFC Uygulama nesnesi (sınıfı) olarak projenize ATL Proje Sihirbazı'nda bildirir. Proje MFC kitaplığını başlatır ve bir sınıf oluşturur (sınıfı *ProjName*) öğesinden türetilen [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Bu seçenek yalnızca nonattributed ATL DLL projeleri kullanılabilir.  
  
```  
class CProjNameApp : public CWinApp  
{  
public:  
 
// Overrides  
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP() 
};  
 
BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)  
END_MESSAGE_MAP()  
 
CProjNameApp theApp;  
 
BOOL CProjNameApp::InitInstance()  
{  
    return CWinApp::InitInstance();

}  
 
int CProjNameApp::ExitInstance()  
{  
    return CWinApp::ExitInstance();

}  
```  
  
 Uygulama nesnesi sınıfı görüntüleyebilir ve kendi `InitInstance` ve `ExitInstance` Sınıf Görünümü'nde işlevleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)   
 [Varsayılan ATL Proje yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

