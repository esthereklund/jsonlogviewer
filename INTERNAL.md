## For internal use

Once the tool is released publicly, it can be downloaded from https://www.nuget.org. Developers can install the tool by using the dotnet tool install command.
Until the package is not uploaded to NuGet you can install it directly from the local `nupkg` folder. For that purpose create first a NuGet package by running the dotnet pack command in the `src/Nyris.JsonLogView` directory:
```
dotnet pack
```
Install the tool from the package by running the [dotnet tool install](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-tool-install) command within the source project directory.
```
dotnet tool install --global --add-source ./nupkg Nyris.JsonLogView
```

>If you are using `zsh`:
>
>The path entry for the .NET Core tools is added during installation as a file `/etc/paths.d/dotnet-cli-tools` with the path entry `~/.dotnet/tools`. The `zsh` doesn't support `~`in the path. So you are likely not to be able to run the tool with zsh.
>
>To solve this issue you would have 2 following options:
>- You switch to the bash to use the tool.
>- You change the path entry and add it to your profile by running the following command:
>```
>cat << \EOF >> ~/.zprofile
># Add .NET Core SDK tools
>export PATH="$PATH:/Users/<USERNAME>/.dotnet/tools"
>EOF
>```
>Run `zsh -l` to make it available for current session.
>
>You can only add the path to the current session by running the following command:
>```
>export PATH="$PATH:/Users/<USERNAME>/.dotnet/tools"
>```
