---
description: 'Daha fazla bilgi edinin: ATL projelerinde MFC desteği'
title: ATL projelerinde MFC desteği
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 8614bfdd5320e0ecdf34cc96251fa8a20f2dede9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157925"
---
# <a name="mfc-support-in-atl-projects"></a>ATL projelerinde MFC desteği

ATL proje sihirbazında **MFC desteği** ' ni seçerseniz, projeniz uygulamayı bir MFC Uygulama nesnesi (sınıf) olarak bildirir. Proje MFC kitaplığını başlatır ve [CWinApp](../../mfc/reference/cwinapp-class.md)'dan türetilmiş bir sınıfı (sınıf *ProjName*) başlatır.

Bu seçenek yalnızca öznitelik olmayan ATL DLL projeleri için kullanılabilir.

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

Uygulama nesne sınıfını ve `InitInstance` ' `ExitInstance` de işlevlerini sınıf görünümü görüntüleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
