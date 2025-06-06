import io.appwrite.Client
import io.appwrite.services.Databases

public void main() {
    Client client = Client(context)
        .setEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
        .setProject("5df5acd0d48c2") // Your project ID
        .setKey("919c2d18fb5d4...a2ae413da83346ad2"); // Your secret API key

    Databases databases = new Databases(client);
    databases.deleteCollection(
        databaseId = "[DATABASE_ID]",
        collectionId = "[COLLECTION_ID]"
        new Continuation<Response>() {
            @NotNull
            @Override
            public CoroutineContext getContext() {
                return EmptyCoroutineContext.INSTANCE;
            }

            @Override
            public void resumeWith(@NotNull Object o) {
                String json = "";
                try {
                    if (o instanceof Result.Failure) {
                        Result.Failure failure = (Result.Failure) o;
                        throw failure.exception;
                    } else {
                        Response response = (Response) o;
                    }
                } catch (Throwable th) {
                    Log.e("ERROR", th.toString());
                }
            }
        }
    );
}