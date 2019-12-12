---
title: Introdução ao .NET Core usando a CLI-CLI do .NET Core
description: Um tutorial passo a passo que mostra como começar a usar o .NET Core no Windows, Linux ou macOS com a CLI (interface de linha de comando) do .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: seodec18,updateeachrelease
ms.openlocfilehash: 4c6a8e495d8532a0ab2e90368663a287731a9af0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884273"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="6aaf6-103">Introdução ao .NET Core no Windows/Linux/macOS usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="6aaf6-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="6aaf6-104">Este artigo mostrará como começar a desenvolver aplicativos de plataformas cruzadas em seu computador usando as ferramentas de CLI do .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-104">This article will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="6aaf6-105">Se não estiver familiarizado com o conjunto de ferramentas da CLI do .NET Core, leia a [Visão geral do SDK do .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="6aaf6-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6aaf6-106">{1&gt;{2&gt;Pré-requisitos&lt;2}&lt;1}</span><span class="sxs-lookup"><span data-stu-id="6aaf6-106">Prerequisites</span></span>

- <span data-ttu-id="6aaf6-107">[SDK do .NET Core 3,1](https://dotnet.microsoft.com/download) ou versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="6aaf6-108">Um editor de texto ou de código de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="6aaf6-109">Olá, Aplicativo de Console.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-109">Hello, Console App!</span></span>

<span data-ttu-id="6aaf6-110">Você pode [exibir ou baixar o código de exemplo](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) do repositório dotnet/samples do GitHub.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="6aaf6-111">Para obter instruções de download, consulte [Exemplos e tutoriais](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="6aaf6-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="6aaf6-112">Abra um prompt de comando e crie uma pasta chamada *Hello*.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="6aaf6-113">Navegue até a pasta que você criou e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="6aaf6-114">Vejamos um breve passo a passo:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="6aaf6-115">[dotnet novo](../tools/dotnet-new.md) cria um arquivo de projeto *Hello. csproj* atualizado com as dependências necessárias para criar um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="6aaf6-116">Ele também cria um *Program.cs*, um arquivo básico que contém o ponto de entrada para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>
    
    <span data-ttu-id="6aaf6-117">*Olá. csproj*:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-117">*Hello.csproj*:</span></span>
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    <span data-ttu-id="6aaf6-118">O arquivo de projeto especifica tudo o que é necessário para restaurar as dependências e compilar o programa.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>
    
    - <span data-ttu-id="6aaf6-119">O elemento `<OutputType>` especifica que estamos criando um executável, em outras palavras, um aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="6aaf6-120">O elemento `<TargetFramework>` especifica qual implementação do .NET Estamos direcionando.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="6aaf6-121">Em um cenário avançado, é possível especificar várias estruturas de destino e criar para todas elas em uma única operação.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="6aaf6-122">Neste tutorial, iremos criar apenas para o .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>
    
    <span data-ttu-id="6aaf6-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-123">*Program.cs*:</span></span>
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    <span data-ttu-id="6aaf6-124">O programa é iniciado pelo `using System`, que significa "colocar tudo no namespace `System` no escopo para este arquivo".</span><span class="sxs-lookup"><span data-stu-id="6aaf6-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="6aaf6-125">O namespace `System` inclui a classe `Console`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-125">The `System` namespace includes the `Console` class.</span></span>
    
    <span data-ttu-id="6aaf6-126">Em seguida, definimos um namespace chamado `Hello`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="6aaf6-127">Você pode alterar isso de acordo com a sua vontade.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-127">You can change this to anything you want.</span></span> <span data-ttu-id="6aaf6-128">Uma classe chamada `Program` é definida dentro desse namespace, com um método `Main` que usa uma matriz de cadeias de caracteres denominada `args`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="6aaf6-129">Essa matriz contém a lista de argumentos passados quando o programa é executado.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="6aaf6-130">Como é, essa matriz não é usada e o programa simplesmente grava o texto "Olá, Mundo!"</span><span class="sxs-lookup"><span data-stu-id="6aaf6-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="6aaf6-131">no console.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-131">to the console.</span></span> <span data-ttu-id="6aaf6-132">Posteriormente, faremos alterações no código que usará esse argumento.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-132">Later, we'll make changes to the code that will make use of this argument.</span></span>
    
    <span data-ttu-id="6aaf6-133">`dotnet new` chama [dotnet Restore](../tools/dotnet-restore.md) implicitamente.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="6aaf6-134">`dotnet restore` chama o [NuGet](https://www.nuget.org/) (gerenciador de pacotes do .NET) para restaurar a árvore de dependências.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="6aaf6-135">O NuGet analisa o arquivo *Hello.csproj*, baixa as dependências definidas no arquivo (ou captura-as de um cache no computador) e grava o arquivo *obj/project.assets.json*, que é necessário para compilar e executar a amostra.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="6aaf6-136">o [dotnet Run](../tools/dotnet-run.md) chama [dotnet Build](../tools/dotnet-build.md) para garantir que os destinos de compilação tenham sido criados e, em seguida, chama `dotnet <assembly.dll>` para executar o aplicativo de destino.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
    
    ```console
    dotnet run

    Hello World!
    ```
    
    <span data-ttu-id="6aaf6-137">Como alternativa, você também pode executar `dotnet build` para compilar o código sem executar os aplicativos de console de compilação.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-137">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="6aaf6-138">Isso resulta em um aplicativo compilado, como um arquivo DLL, com base no nome do projeto.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-138">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="6aaf6-139">Nesse caso, o arquivo criado é chamado *Hello. dll*.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-139">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="6aaf6-140">Esse aplicativo pode ser executado com `dotnet bin\Debug\netcoreapp3.1\Hello.dll` no Windows (use `/` para sistemas não Windows).</span><span class="sxs-lookup"><span data-stu-id="6aaf6-140">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    <span data-ttu-id="6aaf6-141">Quando o aplicativo é compilado, um executável específico do sistema operacional foi criado junto com o `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-141">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="6aaf6-142">No Windows, isso seria `Hello.exe`; no Linux ou no macOS, isso seria `hello`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-142">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="6aaf6-143">Com o exemplo acima, o arquivo é nomeado com `Hello.exe` ou `Hello`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-143">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="6aaf6-144">Você pode executar esse executável diretamente.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-144">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="6aaf6-145">Modificar o programa</span><span class="sxs-lookup"><span data-stu-id="6aaf6-145">Modify the program</span></span>

<span data-ttu-id="6aaf6-146">Vamos alterar o programa um pouco.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-146">Let's change the program a bit.</span></span> <span data-ttu-id="6aaf6-147">Os números de Fibonacci são divertidos, então vamos adicioná-lo e também usar o argumento para saudar a pessoa que está executando o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-147">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="6aaf6-148">Substitua o conteúdo do arquivo *Program.cs* pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-148">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="6aaf6-149">Execute o [Build dotnet](../tools/dotnet-build.md) para compilar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-149">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="6aaf6-150">Execute o programa passando um parâmetro para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-150">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="6aaf6-151">Ao usar o comando `dotnet` para executar um aplicativo, adicione `--` ao final.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-151">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="6aaf6-152">Qualquer coisa à direita de `--` será passada como um parâmetro para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-152">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="6aaf6-153">No exemplo a seguir, o valor `John` é passado para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-153">In the following example, the value `John` is passed to the app.</span></span>

    ```console
    $ dotnet run -- John
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

<span data-ttu-id="6aaf6-154">E pronto.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-154">And that's it!</span></span> <span data-ttu-id="6aaf6-155">Você pode modificar o *Program.cs* da maneira que desejar.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-155">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="6aaf6-156">Trabalhando com vários arquivos</span><span class="sxs-lookup"><span data-stu-id="6aaf6-156">Working with multiple files</span></span>

<span data-ttu-id="6aaf6-157">Arquivos únicos são bons para programas únicos simples, mas se você estiver criando um aplicativo mais complexo, provavelmente terá vários arquivos de código em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-157">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="6aaf6-158">Vamos nos basear no exemplo de Fibonacci anterior armazenando em cache alguns valores de Fibonacci e adicionar alguns recursos recursivos.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-158">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="6aaf6-159">Adicione um novo arquivo no diretório *Hello* chamado *FibonacciGenerator.cs* com o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-159">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="6aaf6-160">Altere o método `Main` no arquivo *Program.cs* para criar uma instância da nova classe e chame seu método como no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-160">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="6aaf6-161">Execute o [Build dotnet](../tools/dotnet-build.md) para compilar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-161">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="6aaf6-162">Execute o aplicativo executando [dotnet executar](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="6aaf6-162">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span> <span data-ttu-id="6aaf6-163">O seguinte código mostra a saída do programa:</span><span class="sxs-lookup"><span data-stu-id="6aaf6-163">The following shows the program output:</span></span>

    ```console
    $ dotnet run
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a><span data-ttu-id="6aaf6-164">Publicar seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="6aaf6-164">Publish your app</span></span>

<span data-ttu-id="6aaf6-165">Quando estiver pronto para distribuir seu aplicativo, use o comando [dotnet Publish](../tools/dotnet-publish.md) para gerar a pasta de _publicação_ no _bin\\Debug\\netcoreapp 3.1\\publish\\_ (use o `/` para sistemas que não sejam Windows).</span><span class="sxs-lookup"><span data-stu-id="6aaf6-165">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="6aaf6-166">Você pode distribuir o conteúdo da pasta _publicar_ para outras plataformas, desde que já tenha instalado o runtime dotnet.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-166">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="6aaf6-167">A saída acima pode diferir com base na pasta atual e no sistema operacional, mas a saída deve ser semelhante.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-167">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="6aaf6-168">Você pode executar o aplicativo publicado com o comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="6aaf6-168">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

<span data-ttu-id="6aaf6-169">Conforme mencionado no início deste artigo, um executável específico do sistema operacional foi criado junto com o `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-169">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="6aaf6-170">No Windows, isso seria `Hello.exe`; no Linux ou no macOS, isso seria `hello`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-170">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="6aaf6-171">Com o exemplo acima, o arquivo é nomeado com `Hello.exe` ou `Hello`.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-171">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="6aaf6-172">Você pode executar esse executável publicado diretamente.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-172">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="6aaf6-173">Conclusão</span><span class="sxs-lookup"><span data-stu-id="6aaf6-173">Conclusion</span></span>

<span data-ttu-id="6aaf6-174">E pronto.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-174">And that's it!</span></span> <span data-ttu-id="6aaf6-175">Agora, é possível começar a usar os conceitos básicos aprendidos aqui para criar seus próprios programas.</span><span class="sxs-lookup"><span data-stu-id="6aaf6-175">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="6aaf6-176">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6aaf6-176">See also</span></span>

- [<span data-ttu-id="6aaf6-177">Organizando e testando projetos com as ferramentas da CLI do .NET Core</span><span class="sxs-lookup"><span data-stu-id="6aaf6-177">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
- [<span data-ttu-id="6aaf6-178">Publicar aplicativos .NET Core com a CLI</span><span class="sxs-lookup"><span data-stu-id="6aaf6-178">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="6aaf6-179">Saiba mais sobre a implantação do aplicativo</span><span class="sxs-lookup"><span data-stu-id="6aaf6-179">Learn more about app deployment</span></span>](../deploying/index.md)