Use Balea only in specific schemes
======================================================

When you are using more than one scheme in your application, you might need to run Balea only in certain schemes. For example, if you are hosting an Mvc application authenticated with cookies, as well as some Api endpoints authenticated with tokens in the same host, you may want to use Balea only in your Api with the JwtBearer scheme.

To configure Balea to run only in specific schemes you should add these schemes in the Balea configuration using **ConfigureServices** method::

      services
        .AddBalea(options =>
        {
            options.AddAuthenticationSchemes("Bearer");
        })
        .AddConfigurationStore(Configuration);

If there is no scheme registered in Balea, it will run in the default authentication scheme configured.

If there are any authenticated scheme configured in Balea, it will run only in those specific schemes.
