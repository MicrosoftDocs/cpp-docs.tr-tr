---
title: ATL projelerinde MFC desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.addmfc
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb6a3c5bae4d973ba74155ab018ebea69b0e2b93
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751406"
---
# <a name="mfc-support-in-atl-projects"></a>ATL projelerinde MFC desteği

Seçerseniz **destek MFC** ATL Proje Sihirbazı'nda uygulamayı bir MFC uygulaması nesne (sınıfı) olarak projenize bildirir. Proje MFC Kitaplığı başlatır ve bir sınıf oluşturur (sınıfı *ProjName*) sınıfından türetilen [CWinApp](../../mfc/reference/cwinapp-class.md).

Bu seçenek yalnızca nonattributed ATL DLL projelerinde kullanılabilir.

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

Uygulama nesnesi sınıfı görüntüleyebilir ve `InitInstance` ve `ExitInstance` Sınıf Görünümü'nde işlevleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
[ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)   
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

